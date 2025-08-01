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


