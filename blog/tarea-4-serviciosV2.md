---
title: "Tarea 4 — Service Auto-Restart with cron (Reinicio de servicios)"
date: 2025-10-16
---

## 🎯 Objective / Objetivo
Check periodically if a service is active; if it’s down, restart it and log the event.
Comprobar periódicamente un servicio; si está caído, reiniciarlo y registrar.

---

## 🖥️ Bash Script — `scriptReUpService.sh`

```bash
#!/bin/bash
SERVICIO="apache2"         # o nginx
LOG="/home/alberto/logs/service_check.log"
mkdir -p "$(dirname "$LOG")"

if systemctl is-active --quiet "$SERVICIO"; then
  echo "$(date '+%F %T') $SERVICIO OK" >> "$LOG"
else
  echo "$(date '+%F %T') $SERVICIO DOWN — restarting" >> "$LOG"
  systemctl restart "$SERVICIO"
fi
Guarda en tu Linux como:
/home/alberto/Escritorio/AVANZADO_cron_y_nmap/cron/scriptReUpService.sh
y dale permisos: chmod +x .../scriptReUpService.sh

⏰ cron — Cada 5 minutos
swift
Copiar código
*/5 * * * * "/home/alberto/Escritorio/AVANZADO_cron_y_nmap/cron/scriptReUpService.sh" >> /home/alberto/logs/cron_debug.log 2>&1
🧪 Test / Prueba
bash
Copiar código
sudo systemctl stop apache2     # o nginx
sleep 360                       # espera ciclo cron
systemctl status apache2
tail -n 50 /home/alberto/logs/service_check.log
📚 Lessons / Lecciones
Automatizar = cuidar sistemas sin estar presentes.

Cada log es una prueba de responsabilidad.

Si una vía falla, busca otra: adaptarse, respirar, continuar.