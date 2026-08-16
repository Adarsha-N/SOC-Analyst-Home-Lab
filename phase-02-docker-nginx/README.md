# Phase 2 — Docker & Nginx Baseline

## Objective

Establish a baseline for the web server, Docker environment, and monitoring stack used in the ABC Technologies SOC home lab.

The purpose of this phase is to understand normal service behavior before conducting controlled security investigations.

---

## 1. Nginx Baseline

Ubuntu Server:

`10.10.20.10`

Nginx is listening on:

`TCP/80`

### Nginx Logs

Nginx logs are stored under:

```text
/var/log/nginx/