## Enumeration

Enumeration is an active information-gathering process used to identify detailed information about the target's systems, users, services, resources, and vulnerabilities. It typically follows initial reconnaissance and scanning.

### Goals of Enumeration:
- Identify active hosts, services, open ports, and their versions.
- Gather information about users, groups, shares, and available resources.
- Discover potential vulnerabilities and misconfigurations.

### Important Steps and Tools:

- **Service & Version Detection:**
  ```bash
  nmap -sV [target]
  ```

- **Operating System Detection:**
  ```bash
  nmap -O [target]
  ```

- **Protocol-specific Enumeration:**
  - **SMB:** `enum4linux`, `smbclient`, `nmap smb-enum-*` scripts
  - **DNS:** `dig`, `host`, `dnsenum`
  - **SNMP:** `snmpwalk`, `snmp-check`

### Integration with Metasploit:

- **Export Nmap Scan Results (XML) for Metasploit:**
  ```bash
  nmap -sV -oX scan.xml [target]
  ```

- **Import XML Results into Metasploit:**
  ```bash
  msfconsole
  msf6 > db_import scan.xml
  ```

This enumeration stage provides essential data required for identifying attack vectors and vulnerabilities.