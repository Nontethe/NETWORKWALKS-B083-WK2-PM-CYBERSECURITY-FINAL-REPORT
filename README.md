# NETWORKWALKS-B083-WK2-PM-CYBERSECURITY-PENETRATION-TESTING-REPORT
FOOTPRINTING &amp; NETWORK SCANNING PHASES
# 🛡️ Penetration Testing – Footprinting & Network Scanning

![Cybersecurity](https://img.shields.io/badge/Focus-Cybersecurity-red)
![Penetration Testing](https://img.shields.io/badge/Project-Penetration%20Testing-blue)
![Kali Linux](https://img.shields.io/badge/OS-Kali%20Linux-557C94)
![Nmap](https://img.shields.io/badge/Tool-Nmap%2FZenmap-green)
![Status](https://img.shields.io/badge/Status-Completed-success)
![Week](https://img.shields.io/badge/Program-Week%2002-orange)

## 👤 Author

**Nontethelelo Mahlangu**

Cybersecurity & Ethical Hacking Intern  
**Program:** Cybersecurity Program – Networkwalks  
**Batch:** B083-Networkwalks  
**Week:** 02  
**Date:** 18 September 2026

---

## 📌 Project Overview

This project documents practical cybersecurity activities completed during **Week 02** of my Cybersecurity & Ethical Hacking internship at **Networkwalks**.

The project focuses on two important penetration-testing phases:

- 🔎 **Phase 1 – Reconnaissance & Footprinting**
- 🌐 **Phase 2 – Network Scanning & Discovery**

The objective was to understand how cybersecurity professionals gather information about a target, identify exposed technologies and DNS infrastructure, discover live devices on an authorized local network, and document security observations.

The practical activities were performed using **Kali Linux, Windows CMD, and Zenmap/Nmap**.

> ⚠️ **Ethical & Legal Notice:**  
> All activities documented in this repository were performed only against systems where I had authorization or systems/networks that I own. This project is intended for educational and authorized cybersecurity research purposes only.

---

# 🎯 Project Objectives

The main objectives of this project were to:

1. Understand the reconnaissance and footprinting phase of penetration testing.
2. Gather publicly available information about a domain.
3. Identify technologies used by a web application.
4. Perform DNS enumeration.
5. Inspect HTTP response headers.
6. Identify whether a Web Application Firewall is present.
7. Understand how attackers build an initial profile of a target.
8. Identify the local IP address and subnet.
9. Discover active hosts on an authorized local network.
10. Identify IP and MAC addresses of discovered devices.
11. Generate a network topology using Zenmap.
12. Document findings and potential security risks professionally.
13. Understand the importance of authorization when performing security testing.

---

# 🧪 Methodology

The project followed a simplified penetration-testing methodology.

```text
┌─────────────────────────────┐
│  Phase 1: Reconnaissance   │
│      & Footprinting         │
└──────────────┬──────────────┘
               │
               ▼
┌─────────────────────────────┐
│ Gather Public Information   │
│ WHOIS / DNS / Web Metadata  │
└──────────────┬──────────────┘
               │
               ▼
┌─────────────────────────────┐
│ Technology Fingerprinting   │
│ WhatWeb / Curl / Wafw00f    │
└──────────────┬──────────────┘
               │
               ▼
┌─────────────────────────────┐
│   Phase 2: Network Scan     │
│       Zenmap / Nmap         │
└──────────────┬──────────────┘
               │
               ▼
┌─────────────────────────────┐
│ Identify Live Hosts         │
│ IP Addresses / MAC Addresses│
└──────────────┬──────────────┘
               │
               ▼
┌─────────────────────────────┐
│ Risk Analysis & Reporting   │
└─────────────────────────────┘
