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

## HTTP Methods

Way for client to show their intended action when making request

GET Request: getting information from web server

POST Request: submitting data to web server and potentially create new records

PUT Request: submitting data to web server to update information

DELETE Request: deleting information/record from a web server

## HTTP Status Codes

Status codes can be broken down into 5 ranges

100-199 - Information Response: first part of request accepted and continue sending rest of request

200-299 - Success: tell client request was succcessful

300-399 - Redirection: redirect client's request to another resource

400-499 - Client Errors: inform client there was an error with request

500-599 - Server Errors: errors occurring on server-side

Most common HTTP responses likely to come across

200 - OK: completed successfully

201 - Created: resource has been created

301 - Moved Permanently: redirect client browsers

302 - Found:  only temporaru change and may change again

400 - Bad Request: missing in request, missing parameter

401 - Not Authorized: not currently allowed to view

403 - Forbidden: do not have permission

405 - Method Not Allowed: does not allow method of request

404 - Page not Found: does not exist

500 - Internal Service Error: error with your request

503 - Service Unavailable: overloaded or down for maintenance

## Headers

Headers are additional bits of data you send to web server when making request, helps with proper view

Common Request Headers

Host: providing host headers can tell which one you require

User-Agent: tells web-server your browser software for proper format

Content-Length: tells web server how much data to expect

Accept-Encoding: tells web-server types of compression methods browser support for trasmitting

Cookie: data sent to server to help remember your information

Common Response Headers

headers returned to client from server after a request

Set-Cookie: Information to store which sent back to web server

Cache-Control: how long to store content of response 

Content-Type: tells client what type of data is being returned

Content-Encoding: method used to compress data to make it smaller when sending over

## Cookies

Small piece of data stored on computer, "Set-Cookie", HTTP is stateless, cookies help remind web server who you are, common for website authentication, cookie value is token and isn't easily humanly guessable

## How websites work

Your browser makes request to web server asking for information about page you're visiting, responds with data browser uses to show you the page, web server is just dedicated computer somewhere else in world that handles your request

Two main components that make up website:

Front End (Client-Side) - way your browser renders a website

Back End (Server-Side) - a server that processes your request and returns a response

## HTML

HTML build websites and define structure

CSS to make websites look pretty by adding style options

JavaScript implements complex features on pages using interactivity

HyperText Markup Language (HTML) is language websites are written in, elements known as tags are building blocks of HTML pages and tell browsers how to display content

The "<!DOCTYPE html>" define page is in HTML5

The "<html>" is root element of HTML page, all other elements come after this element

The "<head>" contains information about page

The "<body>" defines HTML document's body

The "<h1>" element defines a large heading

The "<p>" element defines a paragraph

There are tags for buttons and images and list, etc.

Tags can contain attributes to style elements or src attribute used on images to specify location of image, can have multiple attributes

Elements must have different ID's to identigy them uniquely, to identify it by JavaScript

## JavaScript

(JS) allow pages to become interactive, pages would be static without JS, can be loaded within "<script>" tags or included remotely with the src attribute

JS can find HTMl elements of id and change it's content, onclick and onhover when buttons are clicked

## Sensitive Data Exposure

when a website doesn't properly protect sensitive clear-text information to end-usres, found in site's fronted source code

Can see HTML tags from "view the page source", web developer forget to remove login credential, HTML commets with temporary credentials

## HTML Injection

when unfiltered user input is displayed on page, website fails to sanitize user input, inject HTML code into vulnerable webstie

Client-side where user inputs into a website frontened and input sanitization is important, controlling page appearance and functionality

## Putting it All Together

when you request a website, your computer needs to know server's IP address and it uses DNS

you computer talks to web server using HTTP protocol then webserver returns HTML/JavaScript/CSS and images which your browser then uses to correctly format

## Other Components

when website traffic is high and needs high availability, load balancers ensure high traffic websits can handle load and providing failover if server is unresponsive

Load balancer decides best way to forward request amongst multiple servers, round-robin is algorithm that send it to each server, weighted checks how many request a server is currently dealing with and send to least busy server

Load balancers also perform periodic checks with each server known as health check, load balancers can also stop sending traffic until it responds appropriately again

CDN (Content Delivery Networks): helps cutting down traffic to busy website by allowing you host static  files across thousands of server, nearest server physically located

Databases: webservers can communicate with databases to store and recall data from them (MySQL, MSSQL)

WAF (Web Application Firewall): sits between web request and web server, purpose to protect webserver from hacking (request from real browser or bot), checks for rate limiting (excessive amount of web request)

## How Web Servers Work

web server is software that listens for incoming connection and utilizes HTTP to deliver web content to clients,common webservers are APache, Nginx, and IIS

web server delivers files from called root directory in software settings

Viirtual Hosts

web servers can host multiple websites with different domain names through virtual host, text-based configuration files, if not match default website will be provided

Static vs Dynamic Content

static content is content that never changes like pictures, directly served from webserver with no changes made to them

Dynamic content could change with different request, latest entries, word sensitivity searches

Backend is changes you end up seeing through scripting, everything you see is called frontend

Scripting and Backend languages

PHP, Python, Ruby, NodeJS, Perl, interact with databases and process data























