
How HTTPS Works

When we open:

```text
https://www.google.com
```

The following process happens within milliseconds:

```text
Browser
↓
DNS Resolution
↓
TCP Handshake
↓
TLS Handshake
↓
HTTPS Request
↓
Google Server
↓
HTTPS Response
↓
Browser Render
```

---

# Part 1: HTTP

## What is HTTP?

**HTTP (HyperText Transfer Protocol)** is an **Application Layer (Layer 7)** protocol used for communication between a browser (client) and a web server.

```text
Browser ↔ Web Server
```

HTTP transfers:

- HTML
    
- CSS
    
- JavaScript
    
- Images
    
- Videos
    

---

## Why was HTTP created?

Browsers and web servers needed a **standard language** to communicate.

Example:

```text
Browser:
"Give me Google's homepage."

Server:
"Here is the requested webpage."
```

HTTP became that standard communication protocol.

---

## Problem with HTTP

HTTP sends data in **plain text**.

An attacker can potentially read:

- Usernames
    
- Passwords
    
- Cookies
    
- Messages
    
- Session data
    

This makes HTTP insecure.

---

# Part 2: HTTPS

## What is HTTPS?

```text
HTTPS = HTTP + TLS
```

**HTTPS (HyperText Transfer Protocol Secure)** encrypts communication between the browser and the server.

---

## Why was HTTPS created?

HTTPS protects sensitive information such as:

- Passwords
    
- Banking information
    
- Personal data
    
- User sessions
    
- Cookies
    

---

# HTTP vs HTTPS

|HTTP|HTTPS|
|---|---|
|Not secure|Secure|
|Plain text|Encrypted|
|No TLS|Uses TLS|
|Port 80|Port 443|
|No lock icon|🔒 Lock icon|

---

# Part 3: Ports

## What are Ports?

Ports are **logical doors** that allow different services to run on the same machine.

Example:

```text
Your Laptop

|-- Port 22  → SSH
|-- Port 53  → DNS
|-- Port 80  → HTTP
|-- Port 443 → HTTPS
```

One machine can run multiple services using different ports.

---

## Important Ports to Memorize

|Port|Service|Importance|
|---|---|---|
|22|SSH|⭐⭐⭐⭐⭐|
|53|DNS|⭐⭐⭐⭐⭐|
|67/68|DHCP|⭐⭐⭐⭐|
|80|HTTP|⭐⭐⭐⭐⭐|
|443|HTTPS|⭐⭐⭐⭐⭐|

> Focus on these ports first. No need to memorize dozens of ports.

---

# Part 4: TLS

## What is TLS?

**TLS (Transport Layer Security)** secures communication between the client and server.

TLS provides three important functions:

### 1. Encryption

Protects data from being read by attackers.

### 2. Authentication

Verifies that you're communicating with the legitimate server.

### 3. Integrity

Ensures data was not modified during transmission.

---

# Part 5: TLS Handshake (Simplified)

## Step 1: Client Hello

Browser says:

```text
Hello Google
```

---

## Step 2: Server Hello

Google sends:

```text
Here's my certificate
```

---

## Step 3: Browser Verification

The browser verifies the certificate.

---

## Step 4: Key Exchange

Encryption keys are securely exchanged.

---

## Step 5: Secure Communication Starts

Data transmission now becomes encrypted.

---

# Part 6: Common Real-World Troubleshooting

## Problem: Website is not opening

Possible causes:

### DNS Issue

```text
Domain name cannot be converted to an IP address.
```

---

### TCP Issue

```text
TCP handshake failed.
```

---

### TLS Issue

```text
SSL/TLS certificate expired.
```

---

### Web Server Issue

```text
HTTP service is down.
```

---

### Firewall Issue

```text
Port 443 is blocked.
```

---

# Linux Lab (Hands-On Practice)

## Check Website Headers

```bash
curl -I https://google.com
```

Observe:

```text
HTTP/2 301
server:
location:
```

Purpose:

- Check server response
    
- View HTTP headers
    

---

## Check TLS Connection

```bash
openssl s_client -connect google.com:443
```

Observe:

- Certificate information
    
- TLS version
    
- Cipher suite
    

> Don't worry if it looks complicated. We're only observing for now.

---

## Check Open Ports

```bash
ss -tuln
```

Purpose:

- Display listening ports
    
- View active network services
    

---

# Engineer Mindset 🧠

Scenario:

> "Websites open on my phone but not on my laptop."

Think step by step:

1. Does the laptop have an IP address?
    
2. Is DNS working?
    
3. Can it ping `8.8.8.8`?
    
4. Is port `443` blocked?
    
5. Is a firewall blocking traffic?
    

Always troubleshoot layer by layer.

---

# Quick Notes

## Why does HTTPS use Port 443?

Port `443` is the globally standardized port assigned to HTTPS so browsers and servers know that secure TLS communication should happen on that port.

> Ports are simply agreed-upon door numbers.

---

## Why do websites show the 🔒 lock icon?

The lock icon indicates:

- The website is using HTTPS.
    
- A valid TLS certificate exists.
    
- Communication is encrypted.
    

> The lock icon is **not just because of Port 443**.

---

## If HTTP works but HTTPS doesn't

DNS is usually **not the issue** because the domain is already resolving.

Possible causes:

1. Expired TLS certificate
    
2. Port 443 blocked
    
3. HTTPS service not running
    

---

# Interview Questions

### Basic

1. What is HTTP?
    
2. Why was HTTPS created?
    
3. What is TLS?
    
4. What are the three functions of TLS?
    
5. What is the difference between HTTP and HTTPS?
    
6. Why does HTTPS use Port 443?
    
7. Why do websites display a lock icon?
    

### Intermediate

8. Explain how HTTPS works from entering a URL to rendering the webpage.
    
9. What happens during a TLS handshake?
    
10. What would you check if a website opens on your phone but not on your laptop?
    
11. Why is HTTP considered insecure?
    

---

# Revision Cheat Sheet

```text
HTTP = HyperText Transfer Protocol

HTTPS = HTTP + TLS

TLS provides:
1. Encryption
2. Authentication
3. Integrity

Important Ports:

22  → SSH
53  → DNS
67/68 → DHCP
80  → HTTP
443 → HTTPS

HTTPS Flow:

DNS
↓
TCP Handshake
↓
TLS Handshake
↓
HTTPS Request
↓
HTTPS Response
↓
Browser Render
```

> **Cloud Engineering Note:** Don't memorize everything. Understand the flow and learn how to troubleshoot each layer.