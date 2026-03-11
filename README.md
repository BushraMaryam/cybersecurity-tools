# Cybersecurity Toolkit — SQL Injection Scanner & Network Sniffer

> **Two Python-based offensive security tools: an automated SQL injection vulnerability scanner and a Scapy-based ARP network reconnaissance tool.**

Academic project at NED University (Cybersecurity & Networking modules). Built to understand common attack vectors and network-layer protocols through hands-on implementation.

---

## Disclaimer

These tools are for **educational purposes and authorized security testing only**. Only use them on systems you own or have explicit written permission to test. Unauthorized use is illegal.

---

## Tools

| Tool | File | Purpose |
|------|------|---------|
| SQL Injection Scanner | `SQL-Injection_Scanner.ipynb` | Automated form-based SQLi detection |
| ARP Network Sniffer | `Scapy_IP_and_MAC_address_Sniffer.ipynb` | Network device discovery via ARP broadcast |

---

## Tool 1 — SQL Injection Scanner

Crawls a target URL, extracts HTML forms, and probes each input field with SQL injection payloads. Detects vulnerabilities by analyzing HTTP responses for database error signatures.

### Features:
- **Auto form extraction**: BeautifulSoup parses all `<form>` elements
- **GET & POST support**: Tests both request methods
- **Multi-database detection**: MySQL, MSSQL, Oracle error pattern matching
- **Browser spoofing**: Randomized User-Agent headers
- **Configurable payloads**: Easily extend the injection list

```python
# Example usage
scanner = SQLInjectionScanner("https://target-site.com/login")
scanner.run()
# Output: lists vulnerable fields and injection points
```

---

## Tool 2 — ARP Network Sniffer

Maps all devices on a subnet by broadcasting ARP requests and collecting responses. Built with Scapy for precise packet-level control.

### Features:
- **Full subnet scan**: Discovers all active devices
- **IP → MAC mapping**: Clean output table
- **Configurable timeout**: Adjust for network speed
- **Ethernet frame construction**: Manual ARP request crafting

```python
# Scan a subnet
python sniffer.py 192.168.1.0/24

# Output:
# IP Address        MAC Address
# 192.168.1.1       aa:bb:cc:dd:ee:ff
# 192.168.1.105     11:22:33:44:55:66
```

---



## Tech Stack

- **Network**: Scapy, ARP protocol, Ethernet frames
- **Web**: requests, BeautifulSoup
- **Data**: pandas
- **Language**: Python

---

## Quick Start

```bash
git clone https://github.com/bushramaryam/cybersecurity-tools
pip install scapy requests beautifulsoup4 pandas
```

> **Note**: Scapy requires root/admin privileges for raw packet operations. Run with `sudo python` on Linux/Mac or as Administrator on Windows.

---

## Author

**Bushra Maryam** — AI & Backend Engineer  
[LinkedIn](https://www.linkedin.com/in/bushra-maryam) · [GitHub](https://github.com/BushraMaryam) · [Portfolio](https://bushramaryam.github.io)
