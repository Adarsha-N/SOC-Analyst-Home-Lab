# ABC Technologies SOC Lab — IP Addressing

| Device | Hostname | IP Address | Role |
|---|---|---|---|
| Kali Linux | attacker | 192.168.10.10 | Attacker / Security Testing |
| Firewall | firewall | 192.168.10.1 | Network Firewall |
| Ubuntu Server | webserver | 192.168.10.20 | Web Server / Docker / Nginx |
| Ubuntu Desktop | employee-pc | 192.168.10.30 | Employee Endpoint |
| Monitoring Server | monitor | 192.168.10.40 | Prometheus / Grafana |
| SIEM Server | siem | 192.168.10.50 | Wazuh SIEM |

## Network

- Network: `192.168.10.0/24`
- Gateway: `192.168.10.1`
- Environment: VMware isolated SOC lab network

## Purpose

This addressing plan is used for the ABC Technologies SOC Analyst Home Lab.