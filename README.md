🦈 Beginner Wireshark Packet Capture Lab – Kali Linux + VirtualBox

📌 Overview

This lab demonstrates how to capture and analyze real network traffic using Wireshark within a Kali Linux virtual machine running in VirtualBox. It was designed to help me learn the fundamentals of packet analysis, networking, and tool usage for cybersecurity.

🧰 Tools & Environment

Kali Linux (2025.1c, running in VirtualBox)

VirtualBox with Bridged Adapter networking

Wireshark 4.4.5 (run with sudo)

Terminal tools: ping, curl, wget, ip route, nslookup, dhclient

🛠️ Lab Setup

1. Install Kali Linux in VirtualBox

Download the Kali ISO

Create a VM in VirtualBox

Assign 2GB+ RAM and Bridged Adapter for networking

2. Configure Networking

Switch network adapter to Bridged in VirtualBox settings

Boot into Kali and verify network:

ip a
ip route
ping -c 3 8.8.8.8

If no connection:

sudo dhclient eth0

3. Launch Wireshark

Run in background to avoid terminal lock:

sudo -b wireshark

Select active interface (e.g., eth0)

📶 Packet Capture Tests

✅ ICMP (Ping)

Run:

ping -c 5 google.com

Filter in Wireshark:

icmp

Observe Echo Request and Reply packets

✅ HTTP Traffic

Use a plain HTTP site like neverssl.com:

curl http://neverssl.com

Filter in Wireshark:

http

Follow TCP stream and read full HTML response

✅ DNS Lookup

Use:

nslookup neverssl.com

Filter in Wireshark:

dns

✅ ARP

Filter:

arp

Observe address resolution on LAN

🧠 Key Takeaways

NAT hides traffic from packet sniffers; Bridged mode exposes real traffic

GUI apps like Wireshark should be launched with sudo -b to avoid terminal blocking

HTTP traffic is readable in plain text; HTTPS is encrypted and not easily analyzed

DNS and ARP are great protocols for beginner visibility

📸 Screenshots

Interface setup

ICMP packet view

HTTP stream with raw HTML

DNS request/response pairs

📂 All screenshots are available here: screenshots folder

➡️ For potential employers or reviewers: This folder contains all visual evidence of the hands-on lab execution and verification of packet captures.

🔚 Next Steps

Capture FTP credentials in a lab

Analyze HTTPS negotiation with TLS filter

Try MITM attack simulation with ettercap

Create IDS alert rules based on traffic patterns

✍️ Author

Tuan Ho – Cybersecurity student exploring hands-on labs and packet analysis. [#OpenToVolunteering]

🔗 View this project on GitHub: github.com/CyberTuan/wireshark-packet-analysis-lab
