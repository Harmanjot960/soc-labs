# ⚠️  Web Vulnerabilities
## Topics Covered
- Cross-Site Scripting
- SQL Injection
- LDAP Injection
- Command Injection
- File Inclusion 
- Sensitive Data Exposure
- Broken Authentication
- Security Misconfiguration
- HTML Injection
---
#  Cross-Site Scripting (XSS)
- Injecting malicious JavaScript into web pages
## Indicators
- '<script>' tags in URL or parameters
- Encoded payloads: `%3Cscript%3E`
- JavaScript in unexpected fields
## Example Log
GET /search?q=<script>alert(1)</script>
## Types
- Stored XSS
- Reflected XSS
- DOM-based XSS
## SOC Relevance
- Detect script injections in requests/responses
- Monitor unusual parameters containing scripts
- Investigate phishing pages using JS payloads
---
# SQL Injection (SQLi)
Injecting SQL queries into input fields
## Indicators
- SQL keywords in input:
  - `SELECT`, `UNION`, `OR 1=1`
- `' OR '1'='1` patterns
- Database error messages in responses
## Example Log
POST /login username=admin' OR 1=1 --
## SOC Relevance
- Look for SQL keywords in requests (SELECT, UNION)
- Detect authentication bypass attempts
- Monitor database error messages
---
# LDAP Injection
Manipulating LDAP queries
## Indicators
- Special LDAP characters: `* ( ) & |`
- Abnormal authentication queries
## Example Log
(&(user=*)(password=*))
## SOC Relevance
- Detect abnormal LDAP query patterns
- Monitor authentication systems using LDAP
---
# Command Injection
Executing OS commands via input
## Indicators
- OS commands in input:
  - `; ls`
  - `&& whoami`
- Unusual server responses
## Example Log
GET /ping?host=8.8.8.8; whoami
## SOC Relevance
- Check for command execution logs
- Look for command patterns (ls, whoami, etc.)
- Detect abnormal server behavior
---
# File Inclusion (LFI/RFI)
Loading local or remote files
## Indicators
- Path traversal:
  - `../`
- Access to sensitive files:
  - `/etc/passwd`
## Example Log
GET /index.php?page=../../etc/passwd
## SOC Relevance
- Monitor for data exfiltration
- Detect path traversal (../)
---
# Sensitive Data Exposure
- Weak encryption or no encryption
- Sensitive info in URLs or responses
## Indicators
- HTTP instead of HTTPS
- Credentials in URLs
- Plaintext sensitive data
## Example Log
GET /login?username=admin&password=1234
## SOC Relevance
- Detect exposed credentials in traffic/logs
- Monitor for unencrypted sensitive data
- Identify leaks in responses
---
# Broken Authentication
Weak login/session handling
## Indicators
- Multiple failed logins
- Login attempts from different locations
- Session reuse anomalies
## Example Log
Multiple 401 responses from same IP
## SOC Relevance
- Detect brute force attacks
- Trigger account lockout alerts
- Session anomalies
---
# Security Misconfiguration
Default settings, exposed services
## Indicators
- Access to admin panels
- Default credentials
- Open directories
## Example Log
GET /admin
## SOC Relevance
- Detect exposed admin panels
- Identify unnecessary services
---
# HTML Injection
Injecting malicious HTML into a webpage
## Indicators
- HTML tags in input:
  - `<h1>`, `<iframe>`
- Modified page content
## Example Log
GET /profile?name=<h1>Hacked</h1>
## SOC Relevance
- Detect unusual input in parameters
- Identify defaced or altered web pages
- Monitor for reflected input in responses
---
