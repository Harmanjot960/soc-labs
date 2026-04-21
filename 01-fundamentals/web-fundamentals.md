# 🌐 Web Development for SOC Analysts
## Topics Covered
- DNS (Domain Name System)
- How DNS Works
- DNS Record Types
- JavaScript Basics
- HTTP
- HTTP Methods
- HTTP Status Codes
- HTTP Headers
- Cookies
- How a Website Works
- HTML Basics
- Web Vulnerabilities (Sensitive Data Exposure, HTML Injection)
- Infrastructure Components (Load Balancers, WAF , CDN )
---
# 🌍 DNS (Domain Name System)
DNS translates domain names into IP addresses.
Example:
google.com → 142.x.x.x
## How DNS Works
1. Browser checks cache
2. Query sent to resolver
3. Root server contacted
4. TLD server (.com)
5. Authoritative server
6. IP returned to browser
## DNS Record Types
- A → IPv4
- AAAA → IPv6
- CNAME → Alias
- MX → Mail server
- TXT → Verification
## SOC Relevance
- Detect DNS tunneling (high volume / unusual queries)
- Monitor newly registered or suspicious domains
- Identify malware C2 communication via DNS
---
# ⚙️ JavaScript Basics

JavaScript adds interactivity to web pages.
## Example
alert("Hello World");
## Uses
- Form validation
- Dynamic content
- API requests
## SOC Relevance
- Malicious scripts in web pages (XSS)
- Obfuscated JavaScript used in attacks
- Analyze script behavior in phishing sites
---
# 🌍 HTTP / HTTPS

Protocol used for communication between client and server.
- HTTP → Not secure
- HTTPS → Encrypted using TLS
## Request Flow
Client → Request → Server  
Server → Response → Client  
## SOC Relevance
- Inspect HTTP traffic for suspicious requests
- HTTPS hides payload → rely on metadata/logs
- Detect unusual communication patterns
---
# 🔄 HTTP Methods

- GET → Retrieve data
- POST → Send data
- PUT → Update data
- DELETE → Remove data
- PATCH → Partial update
## SOC Relevance
- Unexpected methods (PUT/DELETE) may indicate abuse
- Monitor POST requests for data exfiltration
- Identify API misuse
---
# 📊 HTTP Status Codes
## 2xx Success
- 200 OK
- 201 Created
## 3xx Redirection
- 301 Moved Permanently
## 4xx Client Errors
- 400 Bad Request
- 401 Unauthorized
- 403 Forbidden
- 404 Not Found
## 5xx Server Errors
- 500 Internal Server Error
- 503 Service Unavailable
## SOC Relevance
- High 404 → scanning activity
- Repeated 401/403 → brute force attempts
- 500 errors → possible exploitation attempts
---
# 📬 HTTP Headers
Metadata sent with requests and responses.
Examples:
- User-Agent → Client info
- Authorization → Credentials
- Content-Type → Data format
- Cookie → Session data
## SOC Relevance
- Suspicious User-Agents (bots/tools)
- Missing/abnormal headers
- Detect credential abuse via Authorization header
---
# 🍪 Cookies

Small pieces of data stored in the browser.
## Uses
- Authentication
- Session management
- Tracking users
## Risks
- Session hijacking
- Cookie theft
## SOC Relevance
- Monitor session anomalies (IP/User-Agent changes)
- Detect stolen or reused session cookies
- Investigate suspicious authentication behavior
---
# 🌐 How a Website Works
1. User enters URL
2. DNS resolves domain → IP
3. Browser sends HTTP request
4. Server processes request
5. Server returns HTML response
6. Browser renders the page
## SOC Relevance
- Understand attack surface across request lifecycle
- Identify where attacks occur (DNS, HTTP, server)
- Trace malicious request flow
---
# 🧱 HTML Basics

HTML defines the structure of a webpage.
## Example
</HTML>
<!DOCTYPE html>
<html>
  <head>
    <title>Page</title>
  </head>
  <body>
    <h1>Hello</h1>
    <p>This is a paragraph</p>
  </body>
</html>

## SOC Relevance
- Identify injected/malicious HTML
- Analyze phishing page structure
- Detect hidden elements used in attacks
---
# ⚠️ Web Vulnerabilities

## 1. Sensitive Data Exposure
- Weak encryption or no encryption
- Sensitive info in URLs or responses
## SOC Relevance
- Detect exposed credentials in traffic/logs
- Monitor for unencrypted sensitive data
- Identify leaks in responses
---
## 2. HTML Injection
Injecting malicious HTML into a webpage
## SOC Relevance
- Detect unusual input in parameters
- Identify defaced or altered web pages
- Monitor for reflected input in responses
- ---
# 🏗️ Infrastructure Components

## 1. Load Balancer
Distributes traffic across multiple servers.
## SOC Relevance
- Logs may show real client IP (X-Forwarded-For)
- Helps identify traffic distribution anomalies
---
## 2. WAF (Web Application Firewall)
Filters and monitors HTTP traffic.
## SOC Relevance
- Detect blocked attack attempts
- Analyze WAF logs for attack patterns
- Identify false positives/negatives
---
## 3. CDN (Content Delivery Network)

Caches content closer to users for faster delivery.
## SOC Relevance
- Source IP may appear as CDN instead of attacker
- Need to trace real IP via headers
- Used to hide origin servers
---


