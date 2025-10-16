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
