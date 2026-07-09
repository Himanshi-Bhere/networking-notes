![[Pasted image 20260609092219.png]]# DNS (Domain Name System)

## What is DNS?

DNS translates human-readable domain names into IP addresses.

Example:

```
google.com↓142.250.xxx.xxx
```

DNS is often called:

> **The Internet's Contacts App**

---

# Why Do We Need DNS?

Without DNS:

```
google.com
```

would become:

```
142.250.xxx.xxx
```

Users would have to memorize IP addresses.

DNS solves this problem.

---

# DNS Port Number

DNS uses:

```
53
```

DNS primarily uses **UDP 53**.

TCP 53 is used for specific operations like zone transfers.

---

# How DNS Resolution Works

```text
Browser

↓

DNS Resolver

↓

Root Server

↓

TLD Server

↓

Authoritative Server

↓

Website IP
```

## Step 1: Browser Cache

Browser checks whether the IP is already stored.

If found:

```
Use cached IP
```

If not:

Proceed to DNS lookup.

---

## Step 2: Recursive DNS Server

The request is sent to a recursive DNS server.

If it already knows the answer:

```
Return IP Address
```

Otherwise:

Continue searching.

---

## Step 3: Root Server

Directs the query to the appropriate TLD server.

---

## Step 4: TLD Server

Handles extensions:

```
.com.net.org
```

Directs the query to the authoritative server.

---

## Step 5: Authoritative Server

Contains the actual IP mapping.

Returns:

```
google.com↓142.250.xxx.xxx
```

---

# DNS Hierarchy

```
Browser Cache↓Recursive DNS Server↓Root Server↓TLD Server↓Authoritative Server↓IP Address Returned
```

---

# Common DNS Records

## A Record

Maps a domain to an IPv4 address.

```
google.com↓142.250.xxx.xxx
```

---

## AAAA Record

Maps a domain to an IPv6 address.

---

## CNAME

Creates an alias.

```
www.example.com↓example.com
```

---

## MX Record

Directs email traffic.

---

## NS Record

Specifies authoritative name servers.

---

## PTR Record

Reverse DNS.

```
IP↓Domain Name
```

---

## TXT Record

Stores administrative and security information.

Used for:

- SPF
- DKIM
- DMARC

---

# DNS Security

## Problem

Traditional DNS is unencrypted.

Attackers may intercept traffic.

---

## DNS over HTTPS (DoH)

Encrypts DNS traffic inside HTTPS.

Benefits:

- Improved privacy
- Protection from interception

---

## Other Security Technologies

- DNSSEC
- DNS over TLS (DoT)
- DNSCrypt

---

# Complete Flow: What Happens When You Type google.com?

```
Browser Cache↓DNS Resolution↓ARP Resolution↓Routing↓TCP 3-Way Handshake↓TLS Handshake↓HTTPS Request↓Server Response↓Browser Render
```

---

# DNS vs DHCP

|DNS|DHCP|
|---|---|
|Converts domain → IP|Assigns IP automatically|
|Port 53|Ports 67/68|
|Helps find servers|Helps configure devices|

---

# Linux Lab

## DNS Lookup

```
nslookup google.com
```

---

## Detailed DNS Information

```
dig google.com
```

---

## Check DNS Configuration

```
cat /etc/resolv.conf
```

---

# Engineer Mindset 🧠

Scenario:

> I can ping 8.8.8.8 but google.com is not opening.

Suspicion:

```
DNS Problem
```

Because:

- Internet connectivity exists
- Domain resolution is failing

---

# Cloud Engineering Concepts

## Why is DNS important in Cloud?

Cloud applications rely on domain names.

Benefits:

- Users don't need to know IP addresses
- IPs can change without affecting users

---

## Why can't users access AWS EC2 private IPs?

Private IPs are not routable on the public internet.

Access requires:

- Public IP
- NAT Gateway
- Load Balancer

---

# Interview Questions

### Basic

1. What is DNS?
2. Why do we need DNS?
3. What is DNS resolution?
4. What is an A Record?
5. What is a CNAME Record?

### Intermediate

6. Explain the DNS hierarchy.
7. Why does DNS use port 53?
8. Difference between DNS and DHCP?
9. Explain what happens when you type google.com.
10. Why is DNS important in cloud computing?

---

# Revision Cheat Sheet

```
DNS = Domain Name System
Converts:Domain → IP Address
Port:53
Hierarchy:Browser Cache
↓
Recursive DNS
↓
Root Server
↓
TLD Server
↓
Authoritative Server
Records:
A → IPv4
AAAA → IPv6
CNAME → Alias
MX → Mail
NS → Name Server
PTR → Reverse DNS
TXT → Security Information
```

> **Cloud Engineering Note:** DNS is one of the most important topics for Cloud Engineers because every cloud service, load balancer, CDN, and application ultimately depends on domain name resolution.