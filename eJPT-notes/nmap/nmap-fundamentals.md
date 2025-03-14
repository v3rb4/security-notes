# Nmap Cheat Sheet

## Firewall Detection & IDS Evasion

### Fragmentation scan

nmap -f [target]

Sends fragmented packets to bypass firewall filtering.

### Custom MTU (Fragment Size)
```bash
nmap -f --mtu [size] [target]

Sets custom fragment size, e.g., --mtu 24, for IDS evasion.

Decoy Scan (Spoofed Sources)

nmap -D RND:10 [target]

Masks the real scanning IP by using multiple random decoy IPs.

Combined IDS Evasion Techniques

nmap -f -T0 --data-length 50 [target]

Uses fragmentation (-f), slow timing (-T0), and random payload data (--data-length) to evade IDS detection.

⸻

Optimizing Nmap Scans
	•	Adjust timing templates: nmap -T[0-5] [target]
(T0 slowest, T5 fastest; recommended: -T4).
	•	Set minimum packet rate:

nmap --min-rate [packets/sec] [target]


	•	Limit retries:

nmap --max-retries [num] [target]

	•	Show only open ports:

nmap --open [target]



⸻

Nmap Output Formats
	•	Normal (human-readable):

nmap -oN scan.txt [target]

	•	XML (easy parsing):

nmap -oX scan.xml [target]

	•	Grepable (for quick parsing):

nmap -oG scan.gnmap [target]