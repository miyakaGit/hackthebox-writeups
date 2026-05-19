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
```
---

## 📡 FTP Access

### Step 2: Connect to FTP
I connected to the FTP service using:

```bash
ftp <target-ip>
```
---

## 📂 Step 3: File Enumeration

After successfully logging into the FTP server, I listed the available files in the directory:

```bash
ls
```

---

## ⬇️ Step 4: File Download

After identifying the file in the FTP directory, I downloaded it to my local machine using the `get` command:

```bash
get <filename>
```
---

## 📖 Step 5: Read the File (Get the Flag)

After downloading the file, I opened it locally to view its contents:

```bash
cat <filename>
```
Inside the file, I found the flag, which completed the challenge:

---

If you want, I can also:
✔ :contentReference[oaicite:0]{index=0}  
✔ or upgrade it to a **professional Hack The Box portfolio writeup (clean + impressive for GitHub)**














