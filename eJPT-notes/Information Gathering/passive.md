# Passive Information Gathering

## Website Recon & Footprinting

### What are we looking for:

- **IP addresses**  
  Use the `host` command – a DNS lookup utility to get public IP addresses and email servers. If a domain has two or more public IPs, it may be using a proxy.
  ```sh
  host example.com
  ```

- **Directories hidden from search engines**  
  - `/robots.txt` – A plain text file that follows the Robots Exclusion Standard. It contains rules that allow or block access for web crawlers to specific paths on the domain or subdomain.
  - `/sitemap.xml` – A sitemap is a roadmap for search engines, listing the pages on a website to improve indexing.

- **Web technologies being used**  
  - **Browser Add-ons for Firefox:** `BuiltWith` or `Wappalyzer` – These tools identify web technologies running on the site, such as widgets, plugins, and a list of subdomains.
  - **WhatWeb Utility (pre-installed on Kali Linux):** An open-source tool designed to detect various technologies used by a website.
    ```sh
    whatweb www.example.com
    ```

- **Website mirroring**  
  - [HTTrack](https://www.httrack.com) – A tool used to download a website's source code and save it to a local directory for offline analysis.
    ```sh
    httrack https://example.com
    ```
**Whois - command line utility in kali
- ```$whois hackersploit.org```
- we can also visit https://who.is
**[Netcraft](https://sitereport.netcraft.com)**
- collects all the information we could obtain manually. Easy to understand format
**DNS recon**
- dnsrecon pre packaged in kali python script that provides the ability to perform: check all NameServer records for zone Transfers
  - [dnsdumpster](https://dnsdumpster.com) handy tool dns recon & research, find & lookup dns records. OSINT for Network Infrastructure 

**WAF Detection with wafw00f (web application firewall**
- - wafw00f pre packaged in kali 
   ```sh
    $wafw00f http://hackertube.net -a
    ```
