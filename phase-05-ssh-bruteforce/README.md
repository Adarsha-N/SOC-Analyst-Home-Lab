# Phase 5 — SSH Brute-Force Detection & Investigation

## Incident ID

INC-005

## Incident Title

Multiple Failed SSH Logins

## Incident Classification

Credential Attack / SSH Authentication Failures

## Severity

Medium

## Status

Closed — Controlled Security Simulation

---

# 1. Objective

Detect and investigate multiple failed SSH authentication attempts against the Ubuntu server.

The activity was intentionally generated from the Kali Linux security-testing workstation as part of the SOC home-lab exercise.

---

# 2. Lab Environment

| System | IP Address | Role |
|---|---|---|
| Kali Linux | 10.10.20.20 | Security testing / attacker simulation |
| Ubuntu Server | 10.10.20.10 | SSH server |

---

# 3. Detection

Ubuntu SSH authentication logs were monitored using:

```bash
sudo grep -a "Failed password" /var/log/auth.log