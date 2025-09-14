**# Nmap Network Scan Project

## 📌 Overview
This project demonstrates how to perform a basic network scan using **Nmap** on a local network.  
The goal was to identify open ports, running services, and analyze their security significance.

## ⚙️ Environment
- **Host OS:** Kali Linux (VM in VirtualBox)  
- **Target Network:** 10.255.64.0/24  
- **Nmap Version:** 7.95  

## 🛠️ Commands Used
### Basic Service Scan
```bash
nmap -sV 10.255.64.0/24
```

### Advanced Scan
```bash
nmap -A <target_ip>
```

- **-sV:** Detects service/version info  
- **-A:** Enables OS detection, version detection, script scanning, and traceroute  

## 🔎 Findings
| Target IP     | Open Port | Protocol | Service / Version | Significance |
|---------------|-----------|----------|------------------|--------------|
| 10.255.64.48  | —         | —        | All filtered (firewall) | Likely protected by firewall, no visible services |
| 10.255.64.211 | 53        | TCP      | dnsmasq 2.51     | DNS resolution service. Outdated version may be vulnerable |
| 10.255.64.85  | —         | —        | All closed       | No active services found |

## 📝 Significance of Discovered Ports
- **Port 53 (DNS):** Critical for hostname resolution. Outdated versions (like `dnsmasq 2.51`) may contain security vulnerabilities.  
- **Filtered Ports:** Indicate firewall protection, which helps hide services but limits visibility.  
- **Closed Ports:** Suggest that no active services are running on that host.  

## ✅ Conclusion
The scan revealed:
- One host running a potentially vulnerable DNS service (`dnsmasq 2.51`).  
- One host protected by a firewall.  
- One host with no active services.  

**Recommendations:**  
- Update the DNS service to the latest version.  
- Continue maintaining firewall protections.  
- Ensure unused services remain closed.  

## 📂 Deliverables
- `nmap_scan_report.pdf` → Detailed scan report with screenshots  
- `screenshots/` → Nmap scan screenshots  
- `README.md` → Explanation of results (this file)  

## 🎥 Demo Video Idea
**"How to Perform a Basic Network Scan with Nmap"**  
- Install Nmap  
- Run a basic scan (`nmap -sV <IP>`)  
- Run an advanced scan (`nmap -A <IP>`)  
- Interpret results and explain significance  
