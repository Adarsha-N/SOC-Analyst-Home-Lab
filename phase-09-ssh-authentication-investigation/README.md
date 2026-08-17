# Phase 9 — SSH & Authentication Investigation

## Objective

Investigate SSH authentication activity on the Ubuntu SOC endpoint and perform a basic SOC-style analysis of:

- Successful SSH logins
- Failed SSH authentication attempts
- Source IP addresses
- Authentication timestamps
- SSH session closures
- Authentication patterns
- Security assessment of the observed activity

---

## Lab Environment

| System | IP Address | Role |
|---|---|---|
| Kali Linux | `10.10.20.20` | SOC analyst / testing machine |
| Ubuntu | `10.10.20.10` | Monitored endpoint |

### Technologies / Tools

- Ubuntu Linux
- Kali Linux
- OpenSSH
- `journalctl`
- `grep`
- `ss`
- Linux authentication logs

---

# 1. SSH Service Baseline

The SSH service was checked using:

```bash
sudo systemctl status ssh --no-pager