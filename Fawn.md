# 🐾 Hack The Box - Fawn Writeup

## 📌 Overview
**Fawn** is a beginner-friendly Hack The Box machine focused on basic network service enumeration. The main objective is to identify an exposed service, gain access, and retrieve the flag.

- **Difficulty:** Very Easy  
- **Category:** Enumeration / FTP  
- **Goal:** Find and retrieve the flag from the target system  

---

## 🔍 Enumeration

### Step 1: Nmap Scan
I started by scanning the target to identify open ports and services:

```bash
nmap -p- -sV <target-ip>
