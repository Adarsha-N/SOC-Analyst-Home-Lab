# Phase 8 — Endpoint Investigation

## Objective

Investigate endpoint activity on the Ubuntu SOC server and establish a relationship between:

- Network connections
- Listening services
- Processes
- Process IDs (PIDs)
- Executable paths
- Command lines
- Working directories

The purpose of this phase is to demonstrate a basic SOC endpoint investigation workflow using Linux process and network telemetry.

---

## 1. Lab Environment

| System | IP Address | Role |
|---|---|---|
| Kali Linux | `10.10.20.20` | Security testing workstation |
| Ubuntu Server | `10.10.20.10` | SOC monitored endpoint |

### Tools Used

- Linux `ps`
- `ss`
- `lsof`
- `/proc`
- Python HTTP server
- `curl`
- Nginx
- Docker
- Prometheus
- Grafana

---

## 2. Endpoint Baseline

Before investigating suspicious activity, the normal endpoint state was recorded.

### Process Baseline

The Ubuntu server was checked using:

```bash
ps aux --sort=-%cpu | head -15