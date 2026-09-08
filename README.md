# Threat-Engineering-and-Detection-Lab
Detection Lab Integrating Elastic as a SIEM and Shuffle as a SOAR

---

## Content
- [Diagram](#Diagram)
- [Hardware](#Hardware)
- [Stack](#Stack)

## Diagram

## Hardware
- ZBOX Mini PC 
- Apple Mac Mini 2012 12GB DDR3 RAM
- Windows 11 VM 6GB RAM

## Stack
| Component | Version | Role | Device 
| - | - | - | - |
| Elasticsearch | 8.6 | Data Storage and Search | DESSVR01
| Kibana | 8.6 | Dashboard and Monitoring | DESSVR01
| Proxmox | 8.7 | Hypervisor | DESSVR02
| Elastic Agent | 9.6 | EDR and Agent Monitoring | DESWIN01
