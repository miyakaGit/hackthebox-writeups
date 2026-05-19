# HTB Machine: Meow

## Objective
The goal of this machine is to perform basic enumeration and gain access using exposed services.

---

## 🛠 Tools Used
- Nmap
- Netcat
- Telnet

---

## Enumeration

I started by scanning the target using Nmap:

The scan showed that **Telnet (port 23)** was open.

---

##  Gaining Access

I connected using Telnet:

After connecting, I successfully accessed the system.

---

## What I Learned
- How to scan open ports using Nmap
- How Telnet service works
- Importance of service enumeration in penetration testing
