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
whats htcat subfinder_example.txt | httpx -silent -status-code -mc 200 -o active_hosts.txt
```
```
cat subfinder_example.txt | httpx -silent -status-code -mc 200 -o active_hosts.txt
```

---

### dirsearch ###
- dirsearch — active web path scanner. Discover hidden or unlisted web paths (for recon or exploitation)
 - It brute-forces directories and files on websites using a wordlist
 - Sends HTTP requests like: /admin, /login.php, /backup.zip
   
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
