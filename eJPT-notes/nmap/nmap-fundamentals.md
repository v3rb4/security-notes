# Nmap Cheat Sheet for eJPT

## Basic Scanning

```bash
nmap [target]                         # Default TCP SYN scan
nmap -sV -O [target]                  # Service version and OS detection
nmap -A [target]                      # Aggressive scan (OS, version, scripts)
nmap -p- [target]                     # Scan all 65535 TCP ports
nmap -p 1-1000 [target]               # Scan port range
nmap -sU [target]                     # UDP scan
```

## Firewall Detection & IDS Evasion

```bash
nmap -f --mtu 24 [target]             # Fragment packets (24-byte size)
nmap -D RND:10 [target]               # Use 10 random decoy IPs
nmap -f -T0 --data-length 50 [target] # Combined evasion techniques
nmap --spoof-mac [MAC|0|vendor] [target] # MAC address spoofing
nmap --source-port 53 [target]        # Source from trusted port
```

## Performance Optimization

```bash
nmap -T[0-5] [target]                 # Timing template (0=slow, 5=fast)
nmap --min-rate 1000 [target]         # Set min packet rate
nmap --max-retries 2 [target]         # Limit retry attempts
nmap -n [target]                      # No DNS resolution
nmap --open [target]                  # Show only open ports
```

## Output Formats

```bash
nmap -oN scan.txt [target]            # Normal output
nmap -oX scan.xml [target]            # XML output
nmap -oG scan.gnmap [target]          # Grepable output
nmap -oA scan [target]                # Save in all formats
```

## NSE Scripts

```bash
nmap -sC [target]                     # Default scripts
nmap --script=[script-name] [target]  # Specific script
nmap --script=[category] [target]     # Script category
```

## Vulnerability Scanning Examples

```bash
# EternalBlue (MS17-010) vulnerability check
nmap -p445 --script smb-vuln-ms17-010 [target]

# BlueKeep (CVE-2019-0708) vulnerability check
nmap -p3389 --script rdp-vuln-cve2019-0708 [target]

# Scan for multiple critical SMB vulnerabilities
nmap -p445 --script "smb-vuln*" [target]

# Scan for all known vulnerabilities
nmap --script vuln [target]
```

## Metasploit Integration

```bash
# Export for Metasploit
nmap -sV -oX scan.xml [target]

# Import to Metasploit
msfconsole
msf6 > db_import scan.xml
msf6 > hosts
msf6 > services
```

## eJPT Practical Examples

```bash
nmap -sn 192.168.1.0/24              # Quick host discovery
nmap -sV -sC -p- -T4 --open [target]  # Complete service enumeration
nmap -sS -T2 -f [target]              # Stealth scan for IDS evasion
```
