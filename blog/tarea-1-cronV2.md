Tarea 1 — tarea-1-cron.md

📁 Coloca este archivo en: blog/tarea-1-cron.md

---
title: "Tarea 1 — Cron & Bash (Programación automática de tareas)"
date: 2025-10-16
---

## 🎯 Objective / Objetivo

**EN:** Understand how to schedule recurring tasks using `cron`, create executable Bash scripts, and verify automation.  
**ES:** Comprender cómo programar tareas automáticas con `cron`, crear scripts Bash ejecutables y verificar su ejecución.

---

## 🔍 Key Concepts / Conceptos Clave

| Concept | Meaning |
|---------|--------|
| `cron` | Daemon that runs scheduled tasks |
| `crontab` | File that defines user cron jobs |
| `* * * * *` | Minute, Hour, Day, Month, Weekday |

#### Basic cron commands:
```bash
crontab -e    # Edit cron jobs
crontab -l    # List cron jobs
crontab -r    # Delete all jobs (danger)

🖥️ Script Example — script.sh
#!/bin/bash
echo "Cron ejecutado el $(date)" >> /home/alberto/cron_test.log


Make executable:

chmod +x /home/alberto/Escritorio/AVANZADO_cron_y_nmap/cron/script.sh

⏰ Cron Scheduling

Run every minute (test):

* * * * * "/home/alberto/Escritorio/AVANZADO_cron_y_nmap/cron/script.sh"


Check log:

cat /home/alberto/cron_test.log

⚠️ Common Errors / Errores Comunes
Error	Solución
Permission denied	chmod +x script.sh
Rutas con espacios	Usar comillas " "
No genera log	Usar ruta absoluta y permisos correctos
🧪 Verification / Verificación
tail -f /home/alberto/cron_test.log
tail -f /var/log/syslog | grep CRON

📚 Lessons / Reflexión Final

“En la resolución de problemas informáticos, como en la vida, aprendí que no hay que rendirse ni frustrarse: la única derrota es no intentarlo.”

Cron enseña disciplina: preparar, ejecutar, esperar, verificar.
Cada error es parte del proceso. Iterar, analizar, modificar, comprobar.


