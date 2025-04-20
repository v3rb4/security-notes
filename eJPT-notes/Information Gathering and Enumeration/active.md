## 🔎 Active Information Gathering

### 🛰 Network Scanning

Netdiscover – identify devices on the local network

netdiscover -i eth0 -r 192.168.2.0/24

Nmap – powerful network scanner

nmap -sV -sC -O -Pn target.com

 - -sV – detect service versions
 - -sC – run default NSE scripts
 - -O – attempt OS detection
 - -Pn – skip host discovery (no ping)

Masscan – extremely fast port scanner

masscan -p1-65535 192.168.1.0/24 --rate=1000

--rate=1000 — limit scan speed to avoid overwhelming the network

### Amass ###

- Amass helps you find all the domains, subdomains, and related IPs that belong to a target — even the hidden or forgotten ones.
```
amass enum -d example.com -brute -active -o active_recon.txt
```

### Nuclei ###

- Nuclei is a fast, flexible vulnerability scanner that uses YAML-based templates.  
It’s widely used for automated recon and vulnerability detection.

```
nuclei -target https://example.com -t ~/nuclei-templates/
```

### httpx ###

- httpx is a fast and multi-purpose HTTP toolkit built to support running multiple probes using a public library. Probes are specific tests or checks to gather information about web servers, URLs, or other HTTP elements. Httpx is designed to maintain result reliability with an increased number of threads. 

```
cat subfinder_example.txt | httpx -silent -status-code -mc 200 -o active_hosts.txt
```

### dirsearch ###

- dirsearch — active web path scanner. Discover hidden or unlisted web paths (for recon or exploitation)
 - It brute-forces directories and files on websites using a wordlist
 - Sends HTTP requests like: /admin, /login.php, /backup.zip
   ```
   dirsearch -u http://example.com
   ```

### OKAdminFinder ###
- OKAdminFinder is an active reconnaissance tool used in web pentesting to brute-force common admin login pages on a target website. It sends HTTP requests to known admin paths and reports which ones exist based on server responses.
 - Scans a target website for common admin login page URLs
 - Uses a predefined wordlist (like /admin, /admin/login, /admin.php, etc.)
 - Reports the URLs that return status codes like 200 OK
 ```
okadminfinder -u https://example.com
```

### 🌐 DNS Reconnaissance

dig – perform DNS zone transfer manually

dig axfr @nsztm1.digi.ninja zonetransfer.me

fierce – semi-automated DNS recon tool

fierce -dns zonetransfer.me

dnsenum – extended DNS reconnaissance

dnsenum zonetransfer.me

Nmap NSE script for DNS zone transfer

nmap --script dns-zone-transfer -p 53 zonetransfer.me

whois and dig basics

whois example.com
dig example.com any
dig +short ns example.com

### Whatweb ###

- WhatWeb is an open-source web scanner used to identify technologies used by a website by sending HTTP requests and analyzing responses. It detects CMS platforms, server types, frameworks, and other web technologies.

 - whatweb http://target.com
 - whatweb -v http://target.com
 - whatweb --aggressive http://target.com
