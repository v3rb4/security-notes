# Nmap Cheat Sheet

## Firewall Detection & IDS Evasion

### Fragmentation Scan with Custom MTU

```bash
nmap -f --mtu [size] [target]
```
Sets custom fragment size (e.g., `--mtu 24`) to evade IDS detection.

### Decoy Scan (Spoofed Sources)

```bash
nmap -D RND:10 [target]
```
Masks the real scanner IP using multiple random decoy IP addresses.

### Combined IDS Evasion Techniques

```bash
nmap -f -T0 --data-length 50 [target]
```
Combines fragmentation (`-f`), very slow timing (`-T0`), and random payload data (`--data-length`) to bypass IDS detection.

---

## Optimizing Nmap Scans

- **Adjust Timing Templates** (`T0` slowest, `T5` fastest; recommended: `-T4`):
  ```bash
  nmap -T[0-5] [target]
  ```

- **Set Minimum Packet Rate:**
  ```bash
  nmap --min-rate [packets/sec] [target]
  ```

- **Limit Retries:**
  ```bash
  nmap --max-retries [num] [target]
  ```

- **Show Only Open Ports:**
  ```bash
  nmap --open [target]
  ```

---

## Nmap Output Formats

- **Normal (Human-Readable):**
  ```bash
  nmap -oN scan.txt [target]
  ```

- **XML (Easy Parsing):**
  ```bash
  nmap -oX scan.xml [target]
  ```

- **Grepable (Quick Parsing):**
  ```bash
  nmap -oG scan.gnmap [target]
<<<<<<< HEAD
=======
  ```
## Importing Nmap Scan Results Into Metasploit

- **Exporting Nmap Scan Results for Metasploit:**
  ```bash
  nmap -sV -oX scan.xml [target]
  ```
>>>>>>> 43ff48b (Updating nmap fundamentals)

- **Importing Nmap XML Results into Metasploit database:**

  ```bash
  msfconsole
  msf6 > db_import scan.xml
  msf6 > hosts
  msf6 > services
  ```
<<<<<<< HEAD
- `db_import` imports scan data for convenient management within Metasploit.
- Commands `hosts` and `services` verify the imported data.
=======
  - `db_import` imports scan data for convenient management within Metasploit.
  - Commands `hosts` and `services` verify the imported data.
>>>>>>> 43ff48b (Updating nmap fundamentals)
