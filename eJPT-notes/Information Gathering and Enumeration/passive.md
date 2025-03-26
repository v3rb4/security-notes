# Passive Information Gathering

## Website Recon

- **host** – DNS lookup to get public IP of a website and email servers.
  ```sh
  host example.com
  ```

- **Hidden directories & files**  
  - `/robots.txt` – Check for hidden files that are excluded from search engines.
  - `/sitemap.xml` – Contains a structured list of website pages.

- **Web technologies used**  
  - `whatweb` – Identifies technologies used on a website.
    ```sh
    whatweb www.example.com
    ```
  - **Firefox Add-ons:** `BuiltWith`, `Wappalyzer` – Identify CMS, plugins, and subdomains.

- **Website mirroring**  
  - [HTTrack](https://www.httrack.com) – Used to download website source.
    ```sh
    httrack https://example.com
    ```
- **AutoRecon**
  - autorecon is a multi-threaded network reconnaissance tool which performs automated enumeration of services.
    ```sh
    autorecon
    ```
- **Whois Lookup**  
  - Command-line utility in Kali Linux.
    ```sh
    whois hackersploit.org
    ```
  - Alternative: [Whois Lookup](https://who.is)

- **[Netcraft](https://sitereport.netcraft.com)**  
  - Collects website information in an easy-to-understand format https://sitereport.netcraft.com

## DNS Recon

- `dnsrecon` – Pre-installed in Kali, retrieves DNS records for a domain.
  ```sh
  dnsrecon -d hackersploit.org
  ```
- [DNSDumpster](https://dnsdumpster.com) – OSINT tool for DNS reconnaissance & research.

## WAF Detection

- `wafw00f` pre packaged in kali – Detects Web Application Firewalls (WAFs).
  ```sh
  wafw00f betsol.com -a
  ```

## Passive subdomain enumeration 
- subfinder is a fast and passive subdomain enumeration tool written in Go. 
 ```sh
  subfinder -d example.com -o results.txt
 ```
- Sublist3r can be used to perform a subdomain brute force (it's not pre installed in kali sudo apt-get install sublist3r)
 ```sh
   sublist3r -d hackersploit.org -e google, yahoo
 ```
## Google dorks
- site:.*example.com, intitle:admin, filetype:pdf, intitle:index of, inurl:passwd.txt etc
- waybackmachine

## Email enumeration 
- theHarvester pre-installed in Kali
      ```sh
    theHarvester -d example -b google,linkedin...
    ```
## Leaked password databases
- haveibeenpwned.com
