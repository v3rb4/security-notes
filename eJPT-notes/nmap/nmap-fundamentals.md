# Nmap Cheat Sheet

**Nmap** is a powerful network scanner used for host discovery, port scanning, service enumeration, OS fingerprinting, and vulnerability assessment.

---

## Basic Scanning

```bash
nmap [target]                         # Default TCP SYN scan
nmap -sV -O [target]                  # Service version and OS detection
nmap -A [target]                      # Aggressive scan (OS, version, scripts)
nmap -p- [target]                     # Scan all 65535 TCP ports
nmap -p 1-1000 [target]               # Scan port range
nmap -sU [target]                     # UDP scan
```

---

## Firewall Detection & IDS Evasion

```bash
nmap -f --mtu 24 [target]             # Fragment packets with custom MTU
nmap -D RND:10 [target]               # Use 10 random decoy IPs
nmap -f -T0 --data-length 50 [target] # Fragmented packets + slow scan + data length
nmap --spoof-mac Apple [target]       # MAC spoofing (example: Apple)
nmap --source-port 53 [target]        # Use trusted source port (e.g., DNS)
```

---

## Performance Optimization

```bash
nmap -T4 [target]                     # Faster scan (T0 slowest, T5 fastest)
nmap --min-rate 1000 [target]         # Set minimum packet rate
nmap --max-retries 2 [target]         # Limit retry attempts
nmap -n [target]                      # Skip DNS resolution
nmap --open [target]                  # Show only open ports
nmap 
```

---

## Output Formats

```bash
nmap -oN scan.txt [target]            # Normal output
nmap -oX scan.xml [target]            # XML output
nmap -oG scan.gnmap [target]          # Grepable output
nmap -oA scan [target]                # All formats (normal + XML + grepable)
```

---

## NSE Scripts (Vulnerability Scanning)

```bash
nmap -sC [target]                            # Default scripts
nmap --script smb-vuln-ms17-010 -p445 [target]   # EternalBlue (MS17-010)
nmap --script rdp-vuln-cve2019-0708 -p3389 [target] # BlueKeep (CVE-2019-0708)
nmap --script "smb-vuln*" -p445 [target]         # Multiple SMB vulnerabilities
nmap --script vuln [target]                    # All known vulns
```

---

## Metasploit Integration

```bash
nmap -sV -oX scan.xml [target]         # Export Nmap scan to XML

msfconsole
msf6 > db_import scan.xml
msf6 > hosts
msf6 > services
```

---

## Practical eJPT Examples

```bash
nmap -sn 192.168.1.0/24                  # Ping sweep (host discovery)
nmap -sV -sC -p- -T4 --open [target]     # Full scan with scripts and version detection
nmap -sS -T2 -f [target]                 # Stealth scan with fragmentation
```
