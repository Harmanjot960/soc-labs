# ⚠️  Web Vulnerabilities
## Topics Covered

- Sensitive Data Exposure
- HTML Injection
---

## ⚠️ Cross-Site Scripting (XSS)

### 🔎 Indicators
- `<script>` tags in URL or parameters
- Encoded payloads: `%3Cscript%3E`
- JavaScript in unexpected fields

### 📊 Example Log
GET /search?q=<script>alert(1)</script>

### 🚨 SOC Actions
- Check affected users/pages
- Identify source IP
- Block or flag malicious requests

---

## ⚠️ SQL Injection (SQLi)

### 🔎 Indicators
- SQL keywords in input:
  - `SELECT`, `UNION`, `OR 1=1`
- `' OR '1'='1` patterns
- Database error messages in responses

### 📊 Example Log
POST /login username=admin' OR 1=1 --

### 🚨 SOC Actions
- Alert on repeated attempts
- Correlate with login failures
- Escalate if DB access suspected

---

## ⚠️ LDAP Injection

### 🔎 Indicators
- Special LDAP characters: `* ( ) & |`
- Abnormal authentication queries

### 📊 Example Log
(&(user=*)(password=*))

### 🚨 SOC Actions
- Monitor authentication logs
- Detect bypass attempts

---

## ⚠️ Command Injection

### 🔎 Indicators
- OS commands in input:
  - `; ls`
  - `&& whoami`
- Unusual server responses

### 📊 Example Log
GET /ping?host=8.8.8.8; whoami

### 🚨 SOC Actions
- Investigate server activity
- Check for command execution logs

---

## ⚠️ File Inclusion (LFI/RFI)

### 🔎 Indicators
- Path traversal:
  - `../`
- Access to sensitive files:
  - `/etc/passwd`

### 📊 Example Log
GET /index.php?page=../../etc/passwd

### 🚨 SOC Actions
- Identify accessed files
- Monitor for data exfiltration

---

## ⚠️ Sensitive Data Exposure

### 🔎 Indicators
- HTTP instead of HTTPS
- Credentials in URLs
- Plaintext sensitive data

### 📊 Example Log
GET /login?username=admin&password=1234

### 🚨 SOC Actions
- Alert on exposed credentials
- Recommend encryption fixes

---

## ⚠️ Broken Authentication

### 🔎 Indicators
- Multiple failed logins
- Login attempts from different locations
- Session reuse anomalies

### 📊 Example Log
Multiple 401 responses from same IP

### 🚨 SOC Actions
- Detect brute force attacks
- Trigger account lockout alerts

---

## ⚠️ Security Misconfiguration

### 🔎 Indicators
- Access to admin panels
- Default credentials
- Open directories

### 📊 Example Log
GET /admin

### 🚨 SOC Actions
- Identify exposed endpoints
- Recommend hardening

---

## ⚠️ HTML Injection

### 🔎 Indicators
- HTML tags in input:
  - `<h1>`, `<iframe>`
- Modified page content

### 📊 Example Log
GET /profile?name=<h1>Hacked</h1>

### 🚨 SOC Actions
- Check affected pages
- Detect defacement attempts

---

# 🔥 SOC Analyst Mindset

- Look for **patterns**, not one request
- Correlate:
  - IP address
  - User behavior
  - Time patterns
- Always ask:
  👉 "Is this normal for this system?"

---

# Sensitive Data Exposure
- Weak encryption or no encryption
- Sensitive info in URLs or responses
## SOC Relevance
- Detect exposed credentials in traffic/logs
- Monitor for unencrypted sensitive data
- Identify leaks in responses
---
# HTML Injection
Injecting malicious HTML into a webpage
## SOC Relevance
- Detect unusual input in parameters
- Identify defaced or altered web pages
- Monitor for reflected input in responses
---
