# Phase 6 — Firewall Monitoring & Blocked Connection Investigation

## Incident ID

INC-006

## Incident Title

Firewall Blocked Unknown TCP Connection

## Classification

Network Security / Firewall Event

## Severity

Medium

## Status

Closed — Controlled Security Simulation

---

# 1. Objective

The objective of this phase was to configure and investigate the Ubuntu UFW firewall and identify blocked network traffic.

A controlled connection attempt was generated from the Kali Linux testing workstation against a non-allowed TCP port on the Ubuntu server.

---

# 2. Lab Environment

| System | IP Address | Role |
|---|---|---|
| Kali Linux | 10.10.20.20 | Security testing workstation |
| Ubuntu Server | 10.10.20.10 | Protected server |

---

# 3. Firewall Baseline

UFW was active on the Ubuntu server.

Firewall policy:

```text
Incoming: DENY
Outgoing: ALLOW
Routed: DENY