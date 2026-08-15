# SOC Analyst Home Lab

## Detect, Investigate and Respond to Security Incidents

A hands-on Security Operations Center (SOC) home lab that simulates an enterprise environment and demonstrates the complete security incident lifecycle.

## Project Scenario

I am working as an L1 SOC Analyst at ABC Technologies.

The organization has reported suspicious activities involving its web server, employee endpoints, authentication systems and network infrastructure.

The objective is to detect, investigate, contain, recover and document these security incidents.

## Architecture

```text
                     ABC TECHNOLOGIES
                           |
                    VMware Lab Network
                           |
          +----------------+----------------+
          |                |                |
        Kali          Ubuntu Server    Employee PC
      Attacker         Web Server       Endpoint
                         |
                       Docker
                         |
                       Nginx
                         |
                  Monitoring Server
                 Prometheus + Grafana
                         |
                      Wazuh SIEM