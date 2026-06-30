# Content Discovery

*Path:* TryHackMe → Junior Penetration Tester → Web Application Security Fundamentals → Content Discovery

---

# Assessment Goal

This room focused on developing a systematic methodology for discovering hidden content within web applications. Unlike visible functionality obtained through manual browsing, content discovery aims to identify resources that are not directly linked but remain publicly accessible.

The assessment combined manual reconnaissance, Open-Source Intelligence (OSINT), and automated enumeration techniques to build a comprehensive understanding of an application's exposed attack surface.

Throughout the room, multiple discovery techniques were analyzed to demonstrate how hidden files, directories, technologies, subdomains, and virtual hosts can reveal valuable intelligence for subsequent security assessments.

---

# Content Discovery Methodology

```text
Target Website
       │
       ▼
Manual Discovery
       │
       ▼
Technology Fingerprinting
       │
       ▼
OSINT Collection
       │
       ▼
Repository Analysis
       │
       ▼
Directory Enumeration
       │
       ▼
Subdomain Enumeration
       │
       ▼
Virtual Host Discovery
       │
       ▼
Complete Attack Surface Mapping
```

Effective content discovery combines manual analysis with automation, ensuring that exposed resources are identified before vulnerability assessment begins.

---

# Manual Discovery – Common Files

The assessment began by manually inspecting common files and directories frequently exposed by web applications.

Typical locations investigated included:

- robots.txt
- sitemap.xml
- favicon.ico
- .well-known/
- README files
- changelog files
- backup files
- administrative directories

---

## Information Gathered

- Hidden directories
- Crawling restrictions
- Website structure
- Administrative endpoints
- Backup resources
- Development artifacts

---

## Example

```text
https://example.com/robots.txt
```

```text
User-agent: *
Disallow: /admin/
Disallow: /backup/
```

---

## Discovery Workflow

```text
Website
    │
    ▼
Common Files
    │
    ▼
Hidden Resources
    │
    ▼
Reconnaissance Data
```

---

### Engineering Observation

Many organizations unintentionally expose sensitive resources through standard files.

Although `robots.txt` is intended to guide search engine crawlers, it frequently discloses directories administrators intended to remain undiscovered.

Manual inspection remains an essential first step before automated scanning.

---

# Manual Discovery – Headers & Framework Stack

HTTP response headers provide valuable intelligence regarding the technologies powering an application.

Headers analyzed included:

- Server
- X-Powered-By
- Set-Cookie
- Content-Type
- Cache-Control
- CSP Headers
- Security Headers

---

## Example

```http
Server: Apache/2.4.57
X-Powered-By: PHP/8.2
```

---

## Framework Identification

Technology fingerprinting may identify:

- Apache
- Nginx
- IIS
- PHP
- ASP.NET
- Node.js
- Django
- Laravel
- WordPress

---

## Header Analysis Workflow

```text
HTTP Response
      │
      ▼
Response Headers
      │
      ▼
Technology Fingerprinting
      │
      ▼
Framework Identification
```

---

### Engineering Observation

Knowing the application's technology stack significantly improves reconnaissance.

Accurate fingerprinting helps identify:

- Framework-specific attack vectors
- Patch levels
- Known vulnerabilities
- Appropriate testing methodologies

Server banners should therefore be minimized whenever possible.

---

# OSINT – Search Engines & Web Tools

Publicly available information was collected using search engines and online reconnaissance platforms.

Common OSINT techniques included:

- Search engine operators (Google Dorks)
- Website indexing
- Cached pages
- Historical information
- DNS lookups
- WHOIS records
- Certificate transparency logs

---

## Example Search Operators

```text
site:example.com
```

```text
site:example.com admin
```

```text
intitle:index.of
```

```text
filetype:pdf
```

---

## Information Gathered

- Public documents
- Login portals
- Employee information
- Indexed directories
- Historical pages
- Public subdomains

---

### Engineering Observation

OSINT requires no interaction with the target infrastructure, making it one of the lowest-risk reconnaissance techniques while often providing high-value intelligence.

---

# OSINT – Repositories & Archives

Public repositories and archival platforms were analyzed for accidentally exposed information.

Sources investigated included:

- Git repositories
- GitHub projects
- GitLab repositories
- Internet Archive
- Public backups

---

## Information Gathered

- API keys
- Configuration files
- Database credentials
- Source code
- Development history
- Deleted application pages

---

## Example

```text
config.php
.env
backup.zip
.git/
```

---

## Repository Discovery Workflow

```text
Public Repository
        │
        ▼
Source Code Review
        │
        ▼
Sensitive Information
        │
        ▼
Security Assessment
```

---

### Engineering Observation

Developers frequently expose sensitive information through public repositories or incomplete cleanup of deployment artifacts.

Repository analysis should always be included during reconnaissance.

---

# Automated Discovery – Gobuster Fundamentals

Automated directory enumeration was performed using Gobuster to discover resources not visible through normal browsing.

---

## Basic Command

```bash
gobuster dir -u http://target.thm -w wordlist.txt
```

---

## Example Output

```text
/admin
/login
/uploads
/images
/dashboard
```

---

## Enumeration Workflow

```text
Target URL
      │
      ▼
Wordlist
      │
      ▼
HTTP Requests
      │
      ▼
Response Analysis
      │
      ▼
Hidden Directories
```

---

## Information Gathered

- Hidden directories
- Administrative portals
- Backup locations
- API endpoints
- Configuration pages
- Upload directories

---

### Engineering Observation

Automated discovery dramatically increases coverage compared to manual browsing.

However, success depends heavily on selecting an appropriate wordlist and interpreting HTTP status codes correctly.

---

# Automated Discovery – Subdomains & Virtual Hosts

The final phase focused on identifying additional services hosted under the same organization.

---

## Subdomain Enumeration

Example command:

```bash
gobuster dns -d example.com -w subdomains.txt
```

---

## Virtual Host Enumeration

Example command:

```bash
gobuster vhost -u http://target.thm -w hosts.txt
```

---

## Discovery Workflow

```text
Primary Domain
       │
       ├── admin.example.com
       ├── dev.example.com
       ├── api.example.com
       └── test.example.com
```

---

## Information Gathered

- Development servers
- Administrative portals
- Internal applications
- API services
- Staging environments
- Test infrastructure

---

### Engineering Observation

Organizations frequently expose additional services through subdomains and virtual hosts.

These systems often receive less security attention than primary production websites, making them valuable targets during penetration testing.

---

# Content Discovery Intelligence Correlation

```text
Manual Discovery
       │
       ▼
Technology Fingerprinting
       │
       ▼
OSINT Collection
       │
       ▼
Repository Analysis
       │
       ▼
Directory Enumeration
       │
       ▼
Subdomain Discovery
       │
       ▼
Virtual Host Discovery
       │
       ▼
Complete Attack Surface Inventory
```

Combining multiple discovery techniques provides significantly greater visibility than relying on any single reconnaissance method.

---

# Engineering Observations

Several important observations emerged during this assessment:

- Manual discovery often reveals valuable low-hanging information.
- HTTP headers expose application technologies and framework details.
- OSINT provides intelligence without interacting directly with the target.
- Public repositories frequently leak sensitive development information.
- Automated directory enumeration expands application visibility.
- Subdomain and virtual host discovery uncover additional attack surfaces.
- Effective reconnaissance is achieved by combining multiple complementary techniques.

---

# Operational Security Considerations

Content discovery generates varying levels of detectable activity.

Potential monitoring sources include:

- Web server access logs
- Web Application Firewalls (WAF)
- IDS/IPS platforms
- SIEM correlation systems
- DNS monitoring
- CDN security services

Manual reconnaissance generally produces minimal network noise, whereas automated enumeration tools such as Gobuster generate significantly more requests and are more likely to trigger defensive monitoring.

---

# Defensive Engineering Perspective

Organizations should adopt proactive measures to reduce unnecessary information exposure:

- Remove development and backup files from production systems.
- Configure restrictive `robots.txt` entries without revealing sensitive paths.
- Minimize server banner information.
- Disable directory listing.
- Protect administrative interfaces with strong authentication.
- Restrict public repository exposure.
- Remove sensitive data from version control history.
- Monitor abnormal directory enumeration activity.
- Secure development and staging environments.
- Regularly perform content discovery assessments against public-facing assets.

---

# Key Technical Takeaways

- Content discovery extends beyond visible application functionality.
- Manual reconnaissance remains an essential first step in web application assessments.
- HTTP headers reveal valuable technology fingerprinting information.
- OSINT enables passive intelligence gathering.
- Public repositories and archived content can expose sensitive information.
- Gobuster efficiently discovers hidden directories and files.
- Subdomain and virtual host enumeration significantly expand attack surface visibility.
- Combining manual, passive, and automated techniques provides comprehensive reconnaissance coverage.

---

# Technologies & Tools Practiced

- Browser-Based Manual Reconnaissance
- HTTP Header Analysis
- Technology Fingerprinting
- Google Dorking
- OSINT Techniques
- Public Repository Analysis
- Archive Reconnaissance
- Gobuster
- Directory Enumeration
- DNS Enumeration
- Virtual Host Enumeration
- Web Application Reconnaissance
- Attack Surface Mapping
