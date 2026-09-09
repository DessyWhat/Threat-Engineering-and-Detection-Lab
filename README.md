# Threat-Engineering-and-Detection-Lab
Detection Lab Integrating Elastic as a SIEM and Shuffle as a SOAR

---

## Content
- [Diagram](#Diagram)
- [Devices](#Devices)
- [Stack](#Stack)

## Diagram

## Devices
| Hardware | Hostname | IP |
| - | - | - |
| Apple Mac Mini 2012 | DESSVR01 | 192.168.1.114 |
| ZBOX Mini PC | DESSVR02 | 192.168.1.115 |
| Windows 11 VM | DESWIN01 | 192.168.1.116 |

## Stack
| Component | Version | Role | Device 
| - | - | - | - |
| Elasticsearch | 8.6 | Data Storage and Search | DESSVR01 |
| Kibana | 8.6 | Dashboard and Monitoring | DESSVR01 |
| Proxmox | 8.7 | Hypervisor | DESSVR02 |
| Elastic Agent | 9.6 | EDR and Agent Monitoring | DESWIN01 |
| Cuckoo Sandbox | 9.6 | Malware Sandboxing | DESSVR01 | 
