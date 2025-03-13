Port Scanning with Nmap
	•	nmap [target] – basic scan.
	•	nmap -p [port_range] [target] – scan specific ports.
	•	nmap -p- [target] – full scan of all ports (1-65535).

Stealth Scan (SYN Scan)
	•	nmap -sS [target] – stealth SYN scan, does not complete the handshake (requires root).
	•	nmap -sT [target] – full TCP connect scan (used when root access is unavailable).

Host Discovery
	•	nmap -Pn [target] – skips host discovery, scans all specified targets.

Service & OS Detection
	•	nmap -sV [target] – detects service versions.
	•	nmap -O [target] – detects the operating system.
	•	nmap -A [target] – enables -O, -sV, -sC, and traceroute.

Nmap Scripting Engine (NSE)
	•	nmap -sC [target] – runs default scripts.
	•	ls -al /usr/share/nmap/scripts | grep -e "mongodb-database" – search for NSE scripts.
	•	nmap --script=[script_name] [target] – runs a specific script.

Firewall Detection & IDS Evasion
	•	nmap -f [target] – packet fragmentation to bypass filters.
	•	nmap --source-port [port] [target] – changes source port to evade ACLs.
	•	nmap --data-length [num] [target] – adds random data to packets to evade detection.

Optimizing Nmap Scans
	•	nmap -T[0-5] [target] – adjusts scanning speed (T4 is a good balance of speed and accuracy).
	•	nmap --min-rate [num] [target] – sets the minimum packet rate for faster scanning.

Nmap Output Format
	•	nmap -oN [file] – saves output in normal format.
	•	nmap -oX [file] – exports results in XML format.
	•	nmap -oG [file] – saves output in grepable format for easy parsing.