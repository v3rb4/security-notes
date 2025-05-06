## Key SMB Ports
- **TCP:** 139, 445
- **UDP:** 137, 138

## Initial Scan
```bash
# Scan UDP ports (SMB uses 137, 138)
nmap -sU --top-ports 25 <target_ip>

# Targeted SMB scan
nmap -p 139,445 -sV <target_ip>
```

## Critical NSE Scripts

### Protocol Check
```bash
# Check SMB protocols - look for SMBv1 (EternalBlue vulnerability)
nmap --script smb-protocols <target_ip>
```

### Security Assessment
```bash
# Check security mode - guest account enabled?
nmap --script smb-security-mode <target_ip>

# Get OS info
nmap --script smb-os-discovery <target_ip>
```

### User Enumeration
```bash
# List logged-in users
nmap --script smb-enum-sessions <target_ip>

# List users with credentials
nmap --script smb-enum-users --script-args smbusername=<username>,smbpassword=<password> <target_ip>

# Anonymous user listing
nmap --script smb-enum-users --script-args smbusername='',smbpassword='' <target_ip>
```

### Share Enumeration
```bash
# List shares
nmap --script smb-enum-shares <target_ip>

# Anonymous share listing
nmap --script smb-enum-shares --script-args smbusername='',smbpassword='' <target_ip>

# List shares AND contents
nmap --script smb-enum-shares,smb-ls --script-args smbusername=<username>,smbpassword=<password> <target_ip>
```

> **Key point:** If IPC$ share has RW permissions, anonymous users can enumerate shares, accounts, etc.

### Additional Enumeration
```bash
# Server statistics
nmap --script smb-server-stats --script-args smbusername=<username>,smbpassword=<password> <target_ip>

# Domain info
nmap --script smb-enum-domains --script-args smbusername=<username>,smbpassword=<password> <target_ip>

# Group enumeration
nmap --script smb-enum-groups --script-args smbusername=<username>,smbpassword=<password> <target_ip>

# Service enumeration
nmap --script smb-enum-services --script-args smbusername=<username>,smbpassword=<password> <target_ip>
```

## Quick Access Tools

### SMBClient
```bash
# List shares anonymously
smbclient -L //<target_ip>/ -N

# Connect to share
smbclient //<target_ip>/<share_name> -N
```

### Enum4Linux (All-in-one)
```bash
# Full SMB enumeration
enum4linux -a <target
