**Nmap**

```
nmap -sU --top-ports 25 : port 137, 138 are udp smb ports. check if open.
```
**Nmap enum scripts**

```
nmap -sU --top-ports 25 <ip>
```

SMB UDP ports

smb-protocols : list supported protocols

if v1 is enabled - EternalBlue exploit?
smb-security-mode : guest account enabled?

smb-os-discovery.nse : NetBIOS computer name and OS

smb-enum-sessions : enum logged in users

smb-enum-sessions --script-args smbusername=,smbpassword=

smb-enum-users.nse : list all users that exist on samba version

smb-enum-users.nse output

smb-enum-shares : enum shares as guest

smb-enum-shares,smb-ls --script-args smbusername=,smbpassword= : Enumerating all the shared folders and drives then running the ls command on all the shared folders.

smb-enum-shares --script-args smbusername=,smbpassword=

if IPC$ share had RW perms - lets anon users enum shares, accounts etc
smb-enum-users --script-args smbusername=,smbpassword=: enum user acc on target sys

smb-server-stats --script-args smbusername=,smbpassword=

smb-enum-domains --script-args smbusername=,smbpassword=

smb-enum-groups --script-args smbusername=,smbpassword=

smb-enum-services --script-args smbusername=,smbpassword=
```
