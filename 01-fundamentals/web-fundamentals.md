# 🌐 Web Development & Security Fundamentals for SOC Analysts

This document covers essential web technologies and security concepts required for Security Operations Center (SOC) analysts.

---

# 🌍 DNS (Domain Name System)

## What is DNS?
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

- Detect DNS tunneling
- Monitor suspicious domains
- Identify malware communication

---

# 🌍 HTTP / HTTPS

## What is HTTP?

Protocol used for communication between client and server.

- HTTP → Not secure
- HTTPS → Encrypted using TLS

## Request Flow

Client → Request → Server  
Server → Response → Client  

---

# 🔄 HTTP Methods

- GET → Retrieve data
- POST → Send data
- PUT → Update data
- DELETE → Remove data
- PATCH → Partial update

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

---

# 📬 HTTP Headers

Metadata sent with requests and responses.

Examples:

- User-Agent → Client info
- Authorization → Credentials
- Content-Type → Data format
- Cookie → Session data

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

---

# 🌐 How a Website Works

1. User enters URL
2. DNS resolves domain → IP
3. Browser sends HTTP request
4. Server processes request
5. Server returns HTML response
6. Browser renders the page

---

# 🧱 HTML Basics

HTML defines the structure of a webpage.

## Example

```html
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

