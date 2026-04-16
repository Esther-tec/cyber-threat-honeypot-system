# Cyber Threat Honeypot System
### Final Year Project | University of Lincoln | 2025–2026

## The Problem
Traditional Intrusion Detection Systems generate false positive rates as high as 99.5%, 
making real threat detection difficult. This project addresses that gap by deploying a 
honeypot system that captures only genuine attack traffic — zero false positives.

## What I Built
A dual-environment virtualised honeypot system deployed on both Oracle VirtualBox 
(controlled lab) and Microsoft Azure (live internet-facing), capturing and analysing 
real-world cyber attack data.

## Key Results
- 513+ organic attacks captured from 17 countries within hours of Azure deployment
- Detected active exploitation of CVE-2025-55182 (80 hits) — a current-year vulnerability
- Zero false positives across 6,000+ on-premises events
- Attack sources mapped across 4 continents including US, UK, Romania, China, Hong Kong

## Tools & Technologies
- **Honeypot Platform:** T-Pot 24.04.1 HIVE (Cowrie, Dionaea, Honeytrap, ElasticPot, ConPot, Suricata IDS)
- **Cloud Infrastructure:** Microsoft Azure (Standard D2s v3, West Europe)
- **Attack Simulation:** Kali Linux, Nmap, Hydra, Metasploit, SQLmap
- **Intelligence & Visualisation:** ELK Stack (Elasticsearch, Logstash, Kibana)
- **Automation:** Python (Azure SDK, multi-cloud Factory design pattern)
- **On-premises:** Oracle VirtualBox, Ubuntu Server 22.04 LTS

## Attack Intelligence Captured
- SSH brute force: 954 attempts (Cowrie) — RockYou wordlist credential patterns
- FTP brute force: 42 attempts (Dionaea) — admin credential targeting
- TCP reconnaissance: 5,000+ events (Honeytrap) — Metasploit port scanning
- Cryptocurrency-targeted credentials: blockchain, solana, validator, miner usernames
- SMB attacks from Hong Kong targeting port 445 — legacy WannaCry-era attack vector

## MITRE ATT&CK Mapping
All captured behaviours mapped across 6 tactical categories:
| Tactic | Technique | Evidence |
|---|---|---|
| Reconnaissance (TA0043) | T1046 Network Service Discovery | Nmap scan, 5000+ Honeytrap events |
| Credential Access (TA0006) | T1110.001 Brute Force | Cowrie 954 attempts, Dionaea 42 attempts |
| Initial Access (TA0001) | T1190 Exploit Public-Facing App | CVE-2025-55182 (80 hits) |
| Discovery (TA0007) | T1046 Network Service Discovery | Metasploit TCP scan |
| Lateral Movement (TA0008) | T1021.002 SMB/Windows Admin | Dionaea port 445, Hong Kong source |
| Collection (TA0009) | T1213 Data from Info Repositories | ElasticPot probing, Censys Inc source |

## Compliance & Ethics
All research conducted in full compliance with:
- UK Computer Misuse Act (1990)
- Data Protection Act (2018) / GDPR
- ISO/IEC 27001
- NIST SP 800-115
- ACM Code of Ethics

## Screenshots
### Live World Attack Map
x<img width="1902" height="887" alt="live map dashboard" src="https://github.com/user-attachments/assets/5ad27f04-f8ee-44cf-ae0d-f295dbed1643" />

### T-Pot Landing Page
<img width="1238" height="905" alt="Landpage of TPOTCE - Copy" src="https://github.com/user-attachments/assets/e2246bbc-0cea-448d-8dd9-ba42758f118b" />


### SQL Attack Data
<img width="1862" height="917" alt="sql 4" src="https://github.com/user-attachments/assets/f4a918eb-2bfd-486c-a19d-069a5a4ebb83" />


### Global Attack Intelligence — Top Countries
<img width="1159" height="915" alt="location dashboard 1" src="https://github.com/user-attachments/assets/7319a1ae-1478-416f-b2eb-82c4ba9b914e" />


## Python Automation Scripts
Two automation scripts developed:
- `tpot_azure_deploy.py` — automates full Azure deployment pipeline
- `tpot_multicloud_deploy.py` — extends to AWS and GCP using Factory design pattern

## What I Learned
- Real-world attackers target internet-facing systems within minutes of deployment
- Organic attacks differ significantly from simulated attacks in credential strategy
- Honeypots provide high-fidelity, zero false-positive intelligence vs traditional IDS
- Cloud infrastructure management and Python automation at production scale
