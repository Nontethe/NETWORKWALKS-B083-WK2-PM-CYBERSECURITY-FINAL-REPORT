# NETWORKWALKS-B083-WK2-PM-CYBERSECURITY-PENETRATION-TESTING-REPORT

# 🛡️ Penetration Testing – Footprinting & Network Scanning

![Cybersecurity](https://img.shields.io/badge/Focus-Cybersecurity-red)
![Penetration Testing](https://img.shields.io/badge/Project-Penetration%20Testing-blue)
![Kali Linux](https://img.shields.io/badge/OS-Kali%20Linux-557C94)
![Nmap](https://img.shields.io/badge/Tool-Nmap%2FZenmap-green)
![Status](https://img.shields.io/badge/Status-Completed-success)
![Week](https://img.shields.io/badge/Program-Week%2002-orange)

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
│ WHOIS / DNS                 │
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
````

---

# 🛠️ Tools & Technologies

| Tool           | Purpose                                            |
| -------------- | -------------------------------------------------- |
| 🐉 Kali Linux  | Penetration-testing and reconnaissance environment |
| 🔎 WHOIS       | Domain registration and name-server information    |
| 🌐 WhatWeb     | Web technology fingerprinting                      |
| 📡 nslookup    | DNS resolution and IP identification               |
| 📨 curl -I     | HTTP response-header inspection                    |
| 🛡️ wafw00f    | Web Application Firewall detection                 |
| 🌐 DNSRecon    | DNS record enumeration                             |
| 🗺️ Zenmap     | Graphical interface for Nmap network scanning      |
| 💻 Windows CMD | Local IP and MAC address identification            |
| 🔍 Nmap        | Network discovery and host identification          |

---

# 🔎 Phase 1 – Reconnaissance & Footprinting

## 1. WHOIS

WHOIS was used to obtain publicly available domain registration information and identify infrastructure-related information such as name servers.

### Objective

The objective was to understand what information about the domain could be obtained through publicly available registration records.

### Security Relevance

Publicly available registration information can contribute to an attacker's understanding of an organization's infrastructure and external footprint.

---

## 2. WhatWeb

WhatWeb was used to fingerprint the technologies used by the target website.

The exercise identified information including:

* WordPress
* WP Download Manager
* Other web technology information exposed by the website

### Security Relevance

Technology and version information can help security professionals identify software that should be reviewed against current security advisories.

---

## 3. nslookup

The `nslookup` command was used to resolve the target domain to an IP address.

Example result observed during the practical:

```text
192.232.216.128
```

### Security Relevance

DNS resolution provides information about where a web service is hosted and can contribute to infrastructure mapping.

---

## 4. curl

The following command was used to inspect HTTP response headers:

```bash
curl -I https://networkwalks.com
```

The response provided HTTP header information and exposed the WordPress REST API endpoint:

```text
/wp-json/
```

### Security Relevance

HTTP headers and application endpoints may provide useful information for technology fingerprinting and further authorized security assessment.

---

## 5. Wafw00f

Wafw00f was used to determine whether a Web Application Firewall was protecting the website.

The exercise identified:

```text
ModSecurity (SpiderLabs)
```

### Security Relevance

Identifying a WAF provides information about the security architecture protecting a web application.

The presence of a WAF does **not** by itself prove that the application is secure or insecure.

---

## 6. DNSRecon

DNSRecon was used to enumerate DNS-related records.

Information observed included:

* Name servers
* Mail servers
* SPF/TXT records
* Service records
* DNS-related information

### Security Relevance

DNS information can help build a broader picture of an organization's external infrastructure.

---

# 🌐 Phase 2 – Network Scanning

## Zenmap / Nmap

Zenmap was used to perform network discovery on my authorized local network.

The practical involved:

1. Identifying the local IP address.
2. Identifying the subnet.
3. Performing a Ping Scan.
4. Identifying live hosts.
5. Collecting IP addresses.
6. Identifying MAC addresses where available.
7. Creating a network topology.

### Scan Type

```text
Ping Scan
```

### Example Command

```bash
nmap -sn 255.255.255.240
```
---

# 📊 Findings & Risk Analysis

The following findings were identified during the practical exercises.

| # | Finding                                | Evidence / Observation                               | Potential Impact                                           | Risk      |
| - | -------------------------------------- | ---------------------------------------------------- | ---------------------------------------------------------- | --------- |
| 1 | Web technology information exposed     | WhatWeb identified WordPress and WP Download Manager | May assist technology fingerprinting and security research | 🟠 Medium |
| 2 | Server IP identifiable                 | nslookup resolved the domain to `192.232.216.128`    | Provides information about the web service infrastructure  | 🟢 Low    |
| 3 | HTTP technical information exposed     | curl returned HTTP response headers and `/wp-json/`  | May assist further enumeration                             | 🟢 Low    |
| 4 | WAF technology identifiable            | Wafw00f identified ModSecurity                       | Reveals part of the application's security architecture    | 🟢 Low    |
| 5 | DNS infrastructure information exposed | DNSRecon identified DNS, mail and service records    | Can assist external infrastructure mapping                 | 🟠 Medium |
| 6 | Multiple live hosts visible            | Zenmap identified live devices on the authorized LAN | Unknown devices may require investigation                  | 🟠 Medium |

### Risk Legend

```text
🔴 Critical
🟠 Medium
🟢 Low
```

> These findings represent **security observations**, not confirmed vulnerabilities. No exploitation or vulnerability validation was performed as part of these modules.

---

# 🖼️ Screenshots & Evidence

<img width="960" height="540" alt="Screenshot-s1" src="https://github.com/user-attachments/assets/e0251833-8225-4e8f-8726-981c65df4479" />

<img width="960" height="540" alt="Screenshot-s2" src="https://github.com/user-attachments/assets/2f8b3cc1-46cc-4f2b-bc96-0ad61904d30c" />

<img width="960" height="540" alt="Screenshot-s3" src="https://github.com/user-attachments/assets/5cdebf12-41d2-4a36-9e51-97e0eb4e57d6" />

<img width="960" height="540" alt="Screenshot-s4" src="https://github.com/user-attachments/assets/b9491cfa-5eeb-4307-8f7d-c15fe57cedf7" />

<img width="960" height="540" alt="Screenshot-s5" src="https://github.com/user-attachments/assets/2dafbcad-c4bd-42c9-9bab-9a0c34a32d4b" />

<img width="960" height="540" alt="Screenshot-s6" src="https://github.com/user-attachments/assets/dd7e0666-ff46-402e-ad58-86944dd4449e" />


## WHOIS

![WHOIS Scan](evidence/01-whois.png)

---

## WhatWeb

![WhatWeb Scan](evidence/02-whatweb.png)

---

## nslookup

![Nslookup Results](evidence/03-nslookup.png)

---

## Curl HTTP Headers

![Curl Headers](evidence/04-curl-headers.png)

---

## Wafw00f

![Wafw00f Results](evidence/05-wafw00f.png)

---

## DNSRecon

![DNSRecon Results](evidence/06-dnsrecon.png)

---

## Windows IP Configuration

<img width="1245" height="437" alt="ZenPicture" src="https://github.com/user-attachments/assets/08d7a078-945e-456e-b971-1ab5acafbc4c" />

---

## Zenmap Network Scan

<img width="1245" height="437" alt="ZenPicture" src="https://github.com/user-attachments/assets/7ab0f46b-5ed5-4f22-b174-61fc7891f445" />

---

## Zenmap Network Topology

<img width="1222" height="773" alt="zen2" src="https://github.com/user-attachments/assets/87351687-6fed-431e-be4d-94fb4d6e097d" />

---

# 🔐 Security Recommendations

Based on the observations from the practical exercises, the following security practices are recommended:

### 1. Keep Software Updated

CMS platforms, plugins and other web technologies should be regularly updated and reviewed against current security advisories.

### 2. Review Publicly Exposed Information

Organizations should regularly review what information about their technologies and infrastructure is publicly visible.

### 3. Review HTTP Headers

HTTP response headers should be reviewed to identify unnecessary technical information that may be exposed.

### 4. Review DNS Records

DNS records should be periodically reviewed to ensure that only required services and information are publicly exposed.

### 5. Configure and Monitor the WAF

Web Application Firewalls should remain enabled, properly configured and monitored.

### 6. Perform Internal Network Discovery

Organizations should periodically discover devices connected to their internal networks.

### 7. Investigate Unknown Devices

Unexpected devices discovered during internal network scans should be investigated and verified.

### 8. Maintain Network Documentation

Network topology, IP addressing and device information should be documented and kept up to date.

### 9. Maintain Proper Authorization

Security testing should always be performed within an approved scope and with appropriate authorization.

---

# 🧠 What I Learned

This project helped me develop a better understanding of the first stages of penetration testing.

### 🔎 Reconnaissance

I learned that reconnaissance is one of the most important stages of a security assessment. Before attempting to test a system, a security professional can gather a significant amount of information from publicly available sources.

### 🌐 DNS Enumeration

I learned how DNS information can reveal useful details about an organization's infrastructure, including name servers, mail servers and other DNS records.

### 🖥️ Web Technology Fingerprinting

Using WhatWeb helped me understand how security professionals identify technologies used by websites.

### 🛡️ WAF Detection

Using Wafw00f helped me understand how Web Application Firewalls can be identified during reconnaissance and how security controls form part of a web application's defensive architecture.

### 📡 Network Scanning

Using Zenmap/Nmap helped me understand how network discovery can identify active devices and provide an overview of a network.

### 🗺️ Network Topology

Creating a topology helped me visualize how devices can be mapped within a network environment.

### 📊 Security Reporting

I learned that identifying information is only one part of cybersecurity. Findings need to be documented clearly, their potential impact should be explained, and appropriate recommendations should be provided.

### ⚖️ Ethical Hacking

Most importantly, I learned that penetration-testing techniques must always be performed within an authorized scope.

---

# 💼 Skills Demonstrated

Through this project, I demonstrated practical exposure to:

* ✅ Cybersecurity fundamentals
* ✅ Ethical hacking principles
* ✅ Reconnaissance
* ✅ Footprinting
* ✅ OSINT fundamentals
* ✅ DNS enumeration
* ✅ WHOIS
* ✅ Web technology fingerprinting
* ✅ HTTP header analysis
* ✅ WAF identification
* ✅ Network discovery
* ✅ Nmap / Zenmap
* ✅ IP addressing
* ✅ MAC address identification
* ✅ Network topology
* ✅ Risk identification
* ✅ Technical documentation
* ✅ Security reporting
* ✅ Authorized security testing

---

# ⚠️ Disclaimer

This repository is intended for **educational and authorized cybersecurity research purposes only**.

The techniques and tools demonstrated in this project should only be used against systems, networks and applications where the tester has explicit permission.

Unauthorized scanning, enumeration, access or exploitation may violate organizational policies and applicable laws.

The author does not encourage unauthorized access or malicious use of the techniques documented in this repository.

---

# 👤 Author

## Nontethelelo Mahlangu

**Cybersecurity & Ethical Hacking Intern**

📌 Networkwalks
📌 Batch: B083
📌 Week 02
📌 Focus: Penetration Testing & Network Security

---

⭐ **This project demonstrates my practical learning journey in cybersecurity, with a focus on reconnaissance, footprinting, network discovery and professional security reporting.**

```


