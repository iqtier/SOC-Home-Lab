# 🔵 SOC Home Lab

![Status](https://img.shields.io/badge/Status-Active-brightgreen)
![SIEM](https://img.shields.io/badge/SIEM-Wazuh_4.7.5-blue)
![Platform](https://img.shields.io/badge/Platform-VirtualBox-orange)

## 📋 Overview
A fully functional Security Operations Center (SOC) 
home lab built from scratch using VirtualBox. 
Designed to simulate a real enterprise environment 
for practicing threat detection, attack simulation, 
and incident response.

---

## 🖧 Lab Architecture

| Machine | Role | IP Address |
|---|---|---|
| pfSense 2.8.1 | Firewall / Gateway | 192.168.1.1 |
| Wazuh SIEM | Security Monitoring | 192.168.1.10 |
| Windows Server 2022 | Active Directory DC | 192.168.1.150 |
| Windows 10 | Monitored Endpoint | 192.168.1.21 |
| Kali Linux | Attack Simulation | 192.168.1.23 |

---

## 🛠️ Tools Used

- **VirtualBox** — Hypervisor
- **pfSense 2.8.1** — Firewall and network gateway
- **Wazuh 4.7.5** — SIEM, EDR, and log management
- **Sysmon** — Endpoint telemetry (SwiftOnSecurity config)
- **Windows Server 2022** — Active Directory (soc.local)
- **Kali Linux** — Attack simulation
- **Nmap** — Network reconnaissance
- **NetExec** — SMB credential testing

---

## 🏗️ What I Built

- Configured **pfSense** as perimeter firewall 
  with WAN/LAN separation and internal routing
- Deployed **Wazuh SIEM** with Indexer, Manager, 
  and Dashboard components on Ubuntu Server
- Built **Active Directory** domain (soc.local) 
  with Windows Server 2022 domain controller
- Installed **Sysmon** on all Windows endpoints 
  using SwiftOnSecurity ruleset for rich telemetry
- Connected **2 active agents** to Wazuh SIEM 
  achieving 100% agent coverage
- Simulated real attacks and detected them 
  in real time via Wazuh dashboard

---

## ⚔️ Attack Simulations

### Attack 1 — Network Reconnaissance
| | |
|---|---|
| **Tool** | Nmap 7.99 |
| **Command** | `nmap -sS -sV -O 192.168.1.150` |
| **MITRE ATT&CK** | T1046 — Network Service Discovery |
| **Result** | Open ports discovered, OS fingerprinted |
| **Detection** | Wazuh generated spike of alerts |

### Attack 2 — SMB Brute Force
| | |
|---|---|
| **Tool** | NetExec |
| **Target** | soc.local\Administrator via SMB port 445 |
| **MITRE ATT&CK** | T1110 — Brute Force |
| **Result** | 10 failed attempts, 0 credentials obtained |
| **Detection** | 23 authentication failures detected |
|  | Brute Force + Pass the Hash flagged |

---

## 📊 Wazuh Dashboard

![Wazuh Dashboard](screenshots/wazuh-dashboard.png)

---

## 👥 Active Agents

![Active Agents](screenshots/active-agents.png)

---

## 📁 Incident Reports

- [IR-2026-001 — SMB Brute Force Attack](incident-reports/IR-2026-001-SMB-BruteForce.pdf)

---

## 🎯 Skills Demonstrated

- Network architecture and segmentation
- SIEM deployment and configuration  
- Endpoint detection and response (EDR)
- Active Directory administration
- Attack simulation and threat detection
- MITRE ATT&CK framework mapping
- Incident documentation and reporting

---

## 📚 References

- [Wazuh Documentation](https://documentation.wazuh.com)
- [MITRE ATT&CK Framework](https://attack.mitre.org)
- [SwiftOnSecurity Sysmon Config](https://github.com/SwiftOnSecurity/sysmon-config)
