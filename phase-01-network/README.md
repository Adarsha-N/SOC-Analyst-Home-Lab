# Phase 1 — Network & Asset Baseline

## Objective

Establish and verify the baseline network environment for the ABC Technologies SOC Analyst Home Lab.

The purpose of this phase is to understand the assets, network connectivity, exposed services, and monitoring infrastructure before performing security investigations.

---

## Lab Environment

The laboratory is implemented using VMware Workstation.

### Assets

| Asset | IP Address | Role |
|---|---|---|
| Kali Linux | 10.10.20.20 | Attacker / Security Testing |
| Ubuntu Server | 10.10.20.10 | Web + Monitoring Server |

---

## Ubuntu Network Interfaces

| Interface | IP Address | Purpose |
|---|---|---|
| ens33 | 192.168.63.133/24 | NAT / Internet Access |
| ens37 | 10.10.20.10/24 | SOC Laboratory Network |

### SOC Network

```text
Network: 10.10.20.0/24