
---

# 📄 **Tarea 4 — `tarea-4-servicios.md`**

**Crea este archivo:**  
📁 `blog/tarea-4-servicios.md`

```markdown
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
