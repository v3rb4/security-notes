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

- **Whois Lookup**  
  - Command-line utility in Kali Linux.
    ```sh
    whois hackersploit.org
    ```
  - Alternative: [Whois Lookup](https://who.is)

- **[Netcraft](https://sitereport.netcraft.com)**  
  - Collects website information in an easy-to-understand format.

## DNS Recon

- `dnsrecon` – Pre-installed in Kali, retrieves DNS records for a domain.
  ```sh
  dnsrecon -d hackersploit.org
  ```
- [DNSDumpster](https://dnsdumpster.com) – OSINT tool for DNS reconnaissance & research.

## WAF Detection

- `wafw00f` – Detects Web Application Firewalls (WAFs).
  ```sh
  wafw00f betsol.com -a
  ```

