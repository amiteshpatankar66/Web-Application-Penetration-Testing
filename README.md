# Web-Application-Penetration-Testing


## Web Application Penetration Testing

**What it is:** A structured security assessment that simulates real-world attacks to identify vulnerabilities in web apps before malicious actors do.

---

### Phases of a Web App Pentest

**1. Reconnaissance**
Passive and active information gathering: subdomains, tech stack, exposed endpoints, metadata, public records (WHOIS, Shodan, Google dorking).

**2. Scanning & Enumeration**
Map the attack surface: directory/file brute-forcing (Gobuster, ffuf), port scanning (Nmap), service fingerprinting, crawling (Burp Suite Spider, OWASP ZAP).

**3. Vulnerability Identification**
Test against known vulnerability classes — primarily the OWASP Top 10:
- Injection (SQLi, Command, LDAP)
- Broken Authentication / Session Management
- Sensitive Data Exposure
- XML External Entities (XXE)
- Broken Access Control (IDOR, privilege escalation)
- Security Misconfiguration
- XSS (Reflected, Stored, DOM)
- Insecure Deserialization
- Using Components with Known Vulnerabilities
- Insufficient Logging & Monitoring

**4. Exploitation**
Confirm vulnerabilities are real and exploitable. Demonstrate impact without causing damage (e.g., extracting a single row of data vs. dumping the whole DB).

**5. Post-Exploitation**
Lateral movement, privilege escalation, persistence checks — within agreed scope.

**6. Reporting**
Document findings with: severity (CVSS score), proof-of-concept, business impact, and remediation steps.

---

### Core Toolset

| Category | Tools |
|---|---|
| Proxy / Interception | Burp Suite, OWASP ZAP |
| Scanning | Nikto, Nuclei, Nessus |
| SQLi | sqlmap |
| Fuzzing | ffuf, wfuzz |
| Directory Brute Force | Gobuster, dirsearch |
| JS Analysis | LinkFinder, JSParser |
| Auth Testing | Hydra, Medusa |
| Recon | Amass, Subfinder, theHarvester |

---

### Common High-Impact Findings

- **IDOR** — accessing other users' data by changing an ID parameter
- **SQLi** — bypassing auth or dumping DB via unsanitized inputs
- **Stored XSS** — persistent script injection affecting all users
- **JWT flaws** — `alg: none`, weak secrets, improper validation
- **SSRF** — making the server fetch internal resources
- **File upload bypass** — uploading webshells by bypassing extension checks
- **Broken access control** — horizontal/vertical privilege escalation

---

### Methodology Frameworks

- **OWASP Testing Guide (OTG)** — most widely used web-specific framework
- **PTES** (Penetration Testing Execution Standard)
- **WSTG** (Web Security Testing Guide) — deep technical checklists

---

