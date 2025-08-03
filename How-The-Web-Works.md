## What is DNS?

Domain Name System provides simple way to communicate with devices on internet through IP address (Ex. 104.26.10.229), 4 sets of digits ranging from 0-255, complicated to remember set of numbers so remembering website domains like www.etc.com is easier

## Domain Hierarchy

TLD (Top-Level Domain): righthand part of domain name like (.com), two types of TLD which is gTLD (Generic Top Level) & ccTLD (Country Code Top Level domain)

gTLD: meant to tell purpose of domain name like commercial, education, government

ccTLD: geographic purposes

Second-Level Domain: first half before the (.com) for example (tryhackme) is second level but limited to 63 characters including TLD, only use a-z, 0-9, and no consecutive hyphens or start/end with them

Subdomain: Sits on left-hand side of second-level domain where a period separates it like (admin.tryhackme.com), same creating restrictions as second-level domain characteristics, usage of multiple subdomains splits with periods to create longer names (pluckers.admin.tryhackme.com) (253 characters or less), no limit to subdomains you can create 

## DNS Record Types

DNS isn't just for websites

A Record: Resolve to IPv4 addresses (Ex. 104.26.10.229)

AAAA Record: Resolve to IPv6 addresses (Ex. 2606:4700:20::681a:be5)

CNAME Record: Resolve to another domain name like subdomain name returns a CNAME record, DNS request would then be made to work out IP address

MX Record: resolves address of the servers that handle email for domain query

TXT Record: free text fields data can be stored, list servers that have authority

## Making a Request

What happens when you make a DNS request?

Requesting a domain name, computer checks local cache to see if previously viewed, if not then request to your Recursive DNS server will be made

Recursive DNS server is provided by ISP, server has local cache of recently looked up popular domains that if results found sent back to computer and request ends (Twitter/Google)

If request not found locally, journey of starting with internet's root DNS servers

Root server acts as DNS backbone to redirect you to top-level domain depending on request like (.com) and referred to proper TLD server that deals with .com addresses

TLD server holds record of where to find authoritative server to answer DNS request (nameserver), multiple nameservers for a domain name in case one goes down and need back up

Authoritative DNS server responsible for storing DNS records for particular domain name and any updates to it, DNS record sent back to recursive DNS for local copy cached for future request, all DNS records come with TTL (Time To Live) number represented in seconds that response saved for locally until looked up again (caching saves)

## What is HTTP? (HyperText Transfer Protocol)

HTTP is what's used whenever you view a website, set of rules used for communicating with web servers for the transmitting of webpage data (HTML, Images, Videos, etc.)

What is HTTPS? (HyperText Transfer Protocol Secure)

Secure version of HTTP, data is encrypted and assures you're talking to the correct web server

## Requests And Responses

When accessing a wensite, browser makes request to web server for assets like images/texts/HTML and downloads the responses, need to tell the browser specifically where and how to access these resources (URLs will help with this)

What is a URL? (Uniform Resource Locator)

An instruction on how to access a resource on the internet

Scheme: Instructs what protocol to use like (HTTP/HTTPS/FTP)

User: some services require authentication so putting user/password into URL to log in

Host: Domain name or IP address of server you wish to access

Port: port you are going to connect to, usually 80 for HTTP, and 443 for HTTPS, can be hosted on any port 1-65535

Path: file name or location of resource trying to access

Query String: extra bits of information that can be sent to requested path

Fragment: reference to location on actual page, pages with long content

Making a Request

It's possible to make a request to web server with one line (GET/HTTP/1.1)

For a much richer web experience, need to send other data as well, other data is called headers 

Example Request:

Get / HTTP/1.1

Host: tryhackme.com
User-agent: Mozilla/5.0 Firefox/87.0
Referer: https://tryhackme.com/

Line 1: sending the GET method  and telling the web server we are using HTTP protocol

Line 2: we tell web server we want that website

Line 3: tell web server using version of browser

Line 4: telling web server that web page referred us to this one

Line 5: HTTP request always end with a blank line to inform web server request has finished

Example Response:

HTTP/1.1 200 OK

Server: nginx/1.15.8
Date: Fri, 09 Apr 2021 13:34:03 GMT
Content-Type: text/html
Content-Length: 98


<html>
<head>
    <title>TryHackMe</title>
</head>
<body>
    Welcome To TryHackMe.com
</body>
</html>

Line 1: tell us version of protocol server is using then followed by status code which tells us request has been completed successfully

Line 2: tells us web server software and version

Line 3: current date and time of web server

Line 4: tells client what sort of information is going to be sent

Line 5: content=length tells client how longe response is/confirm no data missing

Line 6: HTTP response contains blank line to confirm end of response

Line 7-14: information has been requested

## HTTP Method





















