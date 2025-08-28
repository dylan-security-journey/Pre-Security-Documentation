# DNS, HTTP, and Web Technologies

---

## 1. What is DNS?
- **Domain Name System (DNS)** → Provides simple way to communicate with devices on internet.  
- Translates **domain names → IP addresses** (e.g., `104.26.10.229`).  
- Easier to remember domains (`www.example.com`) than numeric IPs.

---

## 2. Domain Hierarchy
- **TLD (Top-Level Domain)** → Right-hand part of domain name (`.com`).  
  - **gTLD** → Generic TLD (e.g., .com, .edu, .gov).  
  - **ccTLD** → Country Code TLD (e.g., .uk, .jp).  
- **Second-Level Domain** → Name before TLD (e.g., `tryhackme.com`).  
- **Subdomain** → Prefix before domain (e.g., `admin.tryhackme.com`).  
  - Can chain multiple subdomains (e.g., `pluckers.admin.tryhackme.com`).  

---

## 3. DNS Record Types
- **A Record** → Resolves to IPv4 address.  
- **AAAA Record** → Resolves to IPv6 address.  
- **CNAME Record** → Alias, resolves to another domain name.  
- **MX Record** → Identifies mail servers for a domain.  
- **TXT Record** → Free text, used for security/authentication policies.  

---

## 4. DNS Resolution Process
1. Computer checks **local cache**.  
2. If not found, request sent to **Recursive DNS server** (usually ISP).  
3. If not cached there, query goes to:  
   - **Root DNS servers** → Direct to TLD (.com, .org, etc.).  
   - **TLD DNS servers** → Direct to authoritative name servers.  
   - **Authoritative DNS servers** → Provide final answer (e.g., IP address).  
4. Response cached locally with **TTL (Time To Live)** value.  

---

## 5. What is HTTP?
- **HTTP (HyperText Transfer Protocol)** → Rules for communicating with web servers.  
- Transfers data: HTML, images, videos, etc.  
- **HTTPS** → Secure version (encrypted, ensures authenticity).  

---

## 6. URLs (Uniform Resource Locator)
Parts of a URL:  
- **Scheme** → Protocol (HTTP, HTTPS, FTP).  
- **User** → Optional authentication.  
- **Host** → Domain name or IP.  
- **Port** → Network port (80 = HTTP, 443 = HTTPS).  
- **Path** → File location.  
- **Query String** → Extra data passed to server.  
- **Fragment** → Reference to location on page.  

---

## 7. HTTP Requests & Responses

### Example Request:
```http
GET / HTTP/1.1
Host: tryhackme.com
User-Agent: Mozilla/5.0 Firefox/87.0
Referer: https://tryhackme.com/























