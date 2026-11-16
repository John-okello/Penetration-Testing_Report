# Penetration Testing Report: Footprinting & Network Scanning Phases (W2-PM-FINAL)

**Author:** John Okello  
**Program / Batch:** B084 — Networkwalks Cybersecurity & Ethical Hacking Internship  
**Date:** 13 November 2026  

---

## 📋 Overview

This repository documents the **Week 2 Final Practical Report (`W2-PM-FINAL`)** covering the initial reconnaissance and network discovery phases of an ethical hacking engagement:

1. **W2-PM4 — Passive Footprinting & OSINT Reconnaissance (`theHarvester`):** Gathering publicly indexed subdomains, host records, IP addresses, and email addresses for `microsoft.com` using public search engines and OSINT repositories.
2. **W2-PM5 — Active Network Scanning & Host Discovery (`Zenmap` / `Nmap 7.99`):** Scanning an authorized local virtual subnet (`172.16.31.128/24`) to identify live hosts, IP addresses, MAC addresses, hardware vendors, and network topology.

---

## 🛠️ Tools & Environment

* **Operating System:** Kali Linux (VMware Fusion)
* **Footprinting Tool:** `theHarvester`
* **Network Scanning Tool:** `Zenmap` (`Nmap 7.99`)
* **Command-Line Utilities:** Kali Linux Terminal (`ip a` / `ifconfig`)

---

## 🔍 Summary of Commands Executed

### 1. Passive Reconnaissance (`theHarvester`)
```bash
# Targeted search engine query via Baidu
theHarvester -d microsoft.com -l 1000 -b baidu

# Multi-source OSINT enumeration across all available engines
theHarvester -d microsoft.com -l 50 -b all
```

### 2. Active Host Discovery (`Zenmap` / `Nmap`)
```bash
# Ping scan across the local VMware subnet (256 IP addresses)
nmap -sn 172.16.31.128/24
```

**Discovered Active Hosts:**

| IP Address | Status | Latency | MAC Address | Hardware Vendor |
| :--- | :--- | :--- | :--- | :--- |
| `172.16.31.1` | Up | `0.00039s` | `3E:22:FB:3C:51:65` | Unknown |
| `172.16.31.2` | Up | `0.00046s` | `00:50:56:EF:1F:7B` | VMware |
| `172.16.31.254` | Up | `0.00069s` | `00:50:56:ED:8D:DB` | VMware |
| `172.16.31.128` | Up | Local Host | — | Local Kali Linux Interface |

---

## 📂 Repository Structure

```text
├── README.md                          # Project overview and summary
├── W2-PM-FINAL_Pentest_Report.pdf     # Full formatted penetration testing report
├── W2-PM-FINAL_Pentest_Report.md      # Markdown version of the report (optional)
└── evidence/                          # Screenshots and exported scan visuals
    ├── 01_theharvester_baidu.png
    ├── 02_theharvester_all.png
    ├── 03_zenmap_ping_scan.png
    └── 04_zenmap_topology.pdf
```

---

## ⚠️ Legal & Ethical Disclaimer

All activities documented in this repository were performed strictly for educational and authorized security assessment purposes:
* Passive OSINT queries were conducted solely against publicly indexed search engine data.
* Active network scanning was performed exclusively within a self-owned local virtual network (`172.16.31.0/24`).
* Do not use any commands, techniques, or findings in this repository against systems without explicit written authorization from the asset owner.
