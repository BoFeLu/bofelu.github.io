---
title: "Tarea 2 — /tmp Cleanup with cron (Limpieza automática de temporales)"
date: 2025-10-16
---

## Objective (EN) / Objetivo (ES)
Delete files in `/tmp` older than 7 days, run daily with cron, and keep a log.

Eliminar ficheros en `/tmp` con más de 7 días, ejecutarlo a diario con cron y registrar la actividad.

---

## Bash script
```bash
#!/bin/bash
LOG_DIR="/home/alberto/logs"
LOG_FILE="$LOG_DIR/limpieza_tmp.log"
mkdir -p "$LOG_DIR"

# -xdev evita cruzar otros sistemas/volúmenes (seguridad)
# -type f solo archivos; -mtime +7: más de 7 días
# -print antes de -delete para registrar qué borra
find /tmp -xdev -type f -mtime +7 -print -delete >> "$LOG_FILE" 2>&1

echo "Cleanup executed on $(date '+%F %T %Z')" >> "$LOG_FILE"
