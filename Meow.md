# HTB Machine: Meow

##  Objective
The goal of this machine is to practice basic network enumeration and gain access to an exposed service.

---

## Tools Used
- Nmap
- Netcat
- Telnet

---

## Enumeration

I started by scanning the target machine using Nmap to identify open ports and services: 

nmap -sV <target-ip>

The scan results showed that **port 23 (Telnet)** was open.

---

## Gaining Access

Since Telnet was available, I connected to the service:

telnet <target-ip>


After connecting, I was able to access the system successfully.

---

##  Post-Access / Result
After gaining access, I verified system access and explored the environment as part of the lab exercise.

---

##  What I Learned
- How to perform basic port scanning using Nmap
- Identification of open services on a target system
- Basic understanding of Telnet and remote service access
- Importance of enumeration before exploitation
