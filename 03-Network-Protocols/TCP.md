# TCP (Transmission Control Protocol)

## Overview

TCP is a **reliable, connection-oriented protocol** that operates at the **Transport Layer (Layer 4)**.

Its main purpose is to ensure that data is delivered:

- Reliably
- In order
- Without loss

Before sending data, TCP establishes a connection between two devices.

---

# Why Was TCP Created?

Data travelling across a network can experience problems such as:

- Packet loss
- Duplicate packets
- Out-of-order packets

TCP was created to solve these problems.

Example:

Without TCP:

```
Packet 1Packet 2Packet 4Packet 7Packet 9
```

Some packets may be lost or arrive in the wrong order.

TCP ensures proper delivery.

---

# Responsibilities of TCP

TCP performs the following tasks:

### Establish a connection

Before communication starts.

### Reliable delivery

Ensures data reaches the destination.

### Ordered delivery

Data arrives in the correct sequence.

### Error detection

Detects transmission errors.

### Retransmission

Resends lost packets.

---

# TCP Three-Way Handshake

TCP uses a three-step process to establish a connection.

```text
Client ------ SYN ------> Server

Client <--- SYN-ACK ----- Server

Client ------ ACK ------> Server
```

---

## Step 1: SYN (Synchronize)

The client says:

```
Can we communicate?
```

---

## Step 2: SYN-ACK (Synchronize + Acknowledge)

The server responds:

```
Yes, I am available.
```

---

## Step 3: ACK (Acknowledgement)

The client confirms:

```
Great, let's start communication.
```

Connection established.

---

# Website Loading Process

When opening:

```
https://www.google.com
```

Flow:

```
Browser↓Browser Cache↓DNS Resolution↓ARP Resolution↓Routing↓TCP Handshake↓TLS Handshake↓HTTP Request↓Server Response↓Browser Render
```

> TCP happens before the webpage loads.

---

# TCP & Ports

TCP uses ports to identify services.

## Common Ports

|Service|Port|
|---|---|
|SSH|22|
|DNS|53|
|HTTP|80|
|HTTPS|443|

---

## Example Connection

```
192.168.1.10:54321↓142.x.x.x:443
```

Where:

- `192.168.1.10` → Laptop IP
- `54321` → Temporary client port
- `142.x.x.x` → Google IP
- `443` → HTTPS service

---

# Linux Lab

## Display Active TCP Connections

```
ss -t
```

or

```
netstat -t
```

---

## Display Listening Ports

```
ss -tuln
```

Observe:

```
ProtocolLocal AddressPortState
```

---

# Troubleshooting Notes

## Scenario

> Website is not opening.

Follow a top-down approach.

### Step 1: Check Network Connectivity

Verify:

- Wi-Fi/Ethernet connection
- IP address assignment

Commands:

```
ip a
```

or

```
ipconfig
```

---

### Step 2: Check DNS

Verify domain name resolution.

Commands:

```
nslookup google.com
```

or

```
dig google.com
```

---

### Step 3: Check Reachability

Commands:

```
ping google.com
```

or

```
ping 8.8.8.8
```

---

### Step 4: Check Ports

Verify whether HTTP/HTTPS services are available.

Commands:

```
ss -tuln
```

---

### Step 5: Check Security Rules

Verify:

- Firewall
- Security Groups
- ACLs

---

# Interview Questions

### Basic

1. What is TCP?
2. Why was TCP created?
3. Why is TCP considered reliable?
4. What are the responsibilities of TCP?

### Intermediate

5. Explain the TCP three-way handshake.
6. What does SYN mean?
7. What does ACK mean?
8. Explain the website loading flow.
9. How would you troubleshoot if a website is not opening?

---

# Quick Revision Cheat Sheet

```
TCP↓Reliable↓Connection OrientedResponsibilities:- Connection Establishment- Ordered Delivery- Error Detection- RetransmissionThree-Way Handshake:SYN↓SYN-ACK↓ACKHTTPS → 443HTTP → 80SSH → 22DNS → 53
```