# 🦈 Beginner Wireshark Packet Capture Lab – Kali Linux + VirtualBox

## 📌 Overview
This lab demonstrates how to capture and analyze real network traffic using Wireshark within a Kali Linux virtual machine running in VirtualBox. It was designed to help me learn the fundamentals of packet analysis, networking, and tool usage for cybersecurity.

---

## 🧰 Tools & Environment
- Kali Linux (2025.1c, running in VirtualBox)
- VirtualBox with Bridged Adapter networking
- Wireshark 4.4.5 (run with sudo)
- Terminal tools: `ping`, `curl`, `wget`, `ip route`, `nslookup`, `dhclient`

---

## 🛠️ Lab Setup

### 1. Install Kali Linux in VirtualBox
- Download the Kali ISO
- Create a VM in VirtualBox
- Assign 2GB+ RAM and Bridged Adapter for networking

### 2. Configure Networking
- Switch network adapter to **Bridged** in VirtualBox settings
- Boot into Kali and verify network:
  ```bash
  ip a
  ip route
  ping -c 3 8.8.8.8
If no connection:

bash
Copy
Edit
sudo dhclient eth0
3. Launch Wireshark
Run in background to avoid terminal lock:

bash
Copy
Edit
sudo -b wireshark
Select active interface (e.g., eth0)

📶 Packet Capture Tests
✅ ICMP (Ping)
bash
Copy
Edit
ping -c 5 google.com
Wireshark filter:

nginx
Copy
Edit
icmp
✅ HTTP Traffic
bash
Copy
Edit
curl http://neverssl.com
Wireshark filter:

nginx
Copy
Edit
http
✅ DNS Lookup
bash
Copy
Edit
nslookup neverssl.com
Wireshark filter:

nginx
Copy
Edit
dns
✅ ARP
Wireshark filter:

nginx
Copy
Edit
arp
🧠 Key Takeaways
NAT hides traffic from packet sniffers; Bridged mode exposes real traffic

GUI apps like Wireshark should be launched with sudo -b to avoid terminal blocking

HTTP traffic is readable in plain text; HTTPS is encrypted and not easily analyzed

DNS and ARP are great protocols for beginner visibility

📸 Screenshots (optional)
Interface setup

ICMP packet view

HTTP stream with raw HTML

DNS request/response pairs

🔚 Next Steps
Capture FTP credentials in a lab

Analyze HTTPS negotiation with TLS filter

Try MITM attack simulation with ettercap

Create IDS alert rules based on traffic patterns

✍️ Author
Tuan Ho – Cybersecurity student exploring hands-on labs and packet analysis.
#OpenToVolunteering

yaml
Copy
Edit


