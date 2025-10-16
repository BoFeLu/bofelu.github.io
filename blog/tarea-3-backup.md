---
title: "Tarea 3 — Automatic Backups with cron (Copias con tar.gz y logs)"
date: 2025-10-16
---

## 🎯 Objective / Objetivo
Create a daily compressed backup (`.tar.gz`) of a directory, log the result, and apply simple rotation (delete old backups).

Crear una copia comprimida diaria (`.tar.gz`), registrar el resultado y rotar copias antiguas.

---

## 🖥️ Bash Script — `scriptBackupTar.sh`

```bash
#!/bin/bash
ORIGEN="/home/alberto/Documentos"
DESTINO="/home/alberto/backups"
LOG="/home/alberto/logs/backup.log"

mkdir -p "$DESTINO" "$(dirname "$LOG")"
FECHA=$(date +'%Y-%m-%d_%H-%M')
ARCHIVO="$DESTINO/backup_${FECHA}.tar.gz"

# Crear backup
tar -czf "$ARCHIVO" "$ORIGEN" 2>>"$LOG"

# Verificar y registrar
if [ -f "$ARCHIVO" ]; then
  echo "Backup OK: $ARCHIVO el $FECHA" >> "$LOG"
else
  echo "ERROR: no se creó $ARCHIVO el $FECHA" >> "$LOG"
fi

# Rotación: más de 30 días
find "$DESTINO" -type f -name 'backup_*.tar.gz' -mtime +30 -delete
