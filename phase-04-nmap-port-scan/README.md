# Phase 4 — Nmap Port Scan Detection & Investigation

## Incident ID

INC-004

## Incident Title

Port Scan Detected

## Incident Classification

Network Reconnaissance / Port Scanning

## Severity

Medium

## Status

Closed — Authorized Security Testing

---

# 1. Objective

Detect, investigate, and document network reconnaissance activity against the Ubuntu server.

The activity was generated intentionally from the Kali Linux security-testing workstation as part of the SOC home-lab exercise.

---

# 2. Lab Environment

| System | IP Address | Role |
|---|---|---|
| Kali Linux | 10.10.20.20 | Security testing / attacker simulation |
| Ubuntu Server | 10.10.20.10 | Web and monitoring server |

---

# 3. Detection

A service-version scan was performed from Kali Linux against the Ubuntu server.

Command:

```bash
nmap -sV 10.10.20.10