# HTB Machine: Fawn

## 🎯 Objective
The goal of this machine is to practice basic FTP enumeration and access files from an exposed service.

---

## 🛠 Tools Used
- Nmap
- FTP client

---

## 🔍 Enumeration

I started by scanning the target using Nmap to identify open ports and services:

```bash id="fawn2"
nmap -sV <target-ip>
