# Phase 10 — Incident Response & Alerting

## Overview

This phase demonstrates a practical SOC incident response workflow
for an SSH authentication anomaly detected on a Linux endpoint.

The investigation follows the incident response lifecycle:

Detection
↓
Triage
↓
Investigation
↓
Containment
↓
Eradication
↓
Recovery
↓
Monitoring
↓
Lessons Learned

---

## Incident Metadata

| Field | Value |
|---|---|
| Incident ID | SOC-2026-001 |
| Incident Type | SSH Authentication Anomaly |
| Severity | Low |
| Status | Monitoring |
| Detection Source | Linux authentication logs |
| Affected Host | 10.10.20.10 |
| Source Host | 10.10.20.20 |
| Analyst | Adarsha |
| Environment | SOC Analyst Home Lab |

---

## 1. Detection

The incident was detected through Linux SSH authentication logs.

Three failed SSH password authentication attempts were observed
against the user account `adhi` from source host `10.10.20.20`.

Previous successful SSH authentications from the same source were
also identified.

---

## 2. Triage

The following evidence was reviewed:

- SSH authentication logs
- Successful SSH authentication events
- Failed SSH authentication events
- SSH session closures
- Endpoint IP configuration
- Routing table
- Active network connections
- Running services
- UFW firewall status
- Fail2ban status

---

## 3. Investigation Findings

### Authentication Activity

Three failed SSH password attempts were observed:

```text
Source: 10.10.20.20
Target: adhi
Protocol: SSH
Authentication: Password
Failed Attempts: 3