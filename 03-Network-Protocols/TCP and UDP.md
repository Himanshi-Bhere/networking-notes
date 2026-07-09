# TCP, UDP & TCP Three-Way Handshake

## Overview

The **Transport Layer (Layer 4)** determines **how data is delivered** between applications running on different devices.

The two primary protocols used are:

- TCP (Transmission Control Protocol)
- UDP (User Datagram Protocol)

---

# TCP (Transmission Control Protocol)

## What is TCP?

TCP is a **connection-oriented** protocol that focuses on **reliability**.

It ensures:

- Data arrives correctly
- Data arrives in order
- Lost data is retransmitted

TCP is used when accuracy is more important than speed.

---

## Where is TCP used?

Examples:

- Web pages
- HTTPS websites
- File transfers
- Emails

---

# UDP (User Datagram Protocol)

## What is UDP?

UDP is a **connectionless** protocol that focuses on **speed**.

It sends data continuously without checking whether packets arrived successfully.

UDP prioritizes speed over reliability.

---

## Where is UDP used?

Examples:

- Video streaming
- Online gaming
- Voice calls

If a few packets are lost, communication continues instead of waiting for retransmission.

---

# TCP vs UDP

| TCP                  | UDP                |
| -------------------- | ------------------ |
| Reliable             | Fast               |
| Connection-oriented  | Connectionless     |
| Uses acknowledgments | No acknowledgments |
| Slower               | Faster             |
| Used for web pages   | Used for streaming |

---

# What are Ports?

Ports are logical communication channels that differentiate services running on a device.

Example:

```
192.168.1.10:443
```

- `192.168.1.10` → Device
- `443` → Specific service

---

# What are Ephemeral Ports?

Ephemeral ports are temporary source ports automatically assigned by the operating system.

They help distinguish multiple active connections.

Example:

```
Browser → Temporary PortSpotify → Temporary PortTeams → Temporary Port
```

---

# Important Port Numbers

| Port | Service     | Protocol |
| ---- | ----------- | -------- |
| 22   | SSH         | TCP      |
| 23   | Telnet      | TCP      |
| 53   | DNS         | TCP/UDP  |
| 67   | DHCP Server | UDP      |
| 68   | DHCP Client | UDP      |
| 69   | TFTP        | UDP      |
| 80   | HTTP        | TCP      |
| 123  | NTP         | UDP      |
| 443  | HTTPS       | TCP      |
| 587  | SMTP        | TCP      |
| 161  | SNMP        | UDP      |
| 162  | SNMP Traps  | UDP      |
| 3389 | RDP         | TCP/UDP  |

> Focus on understanding the purpose of each service instead of memorizing every port number at once.

---

# TCP Three-Way Handshake

Before exchanging data, TCP establishes a reliable connection.

There are three steps.

---

## Step 1: SYN (Synchronize)

The client sends:

```
Hello, I want to establish a connection.
```

---

## Step 2: SYN-ACK

The server replies:

```
I received your request and I'm ready.
```

---

## Step 3: ACK

The client responds:

```
Acknowledged. Let's start communication.
```

Connection established.

---

# Visual Flow

```
Client↓SYN↓Server↓SYN-ACK↓Client↓ACK↓Data Transfer Begins
```

---

# Real-World Example

## Opening YouTube

Different protocols may be used together.

Example:

### TCP

Used for:

- Loading webpage structure
- Loading website data

### UDP

Used for:

- Streaming video content

This balances reliability and speed.

---

# Linux Lab

## Display Active Connections

```
ss -tun
```

---

## Display Listening Ports

```
ss -tuln
```

---

## Display Running Connections with Processes

```
ss -tpn
```

---

# Troubleshooting Notes

### Scenario

> Website is slow or not opening.

Check:

1. Is DNS working?
2. Is TCP handshake completing?
3. Is port 443 open?
4. Is the firewall blocking traffic?
5. Is the application listening?

---

# Interview Questions

### Basic

1. What is TCP?
2. What is UDP?
3. Difference between TCP and UDP?
4. What are ports?
5. What are ephemeral ports?

### Intermediate

6. Explain the TCP three-way handshake.
7. Why is TCP considered reliable?
8. Why is UDP used for streaming?
9. Which protocol would you choose for video calls and why?

---

# Quick Revision Cheat Sheet

```
TCP↓Reliable↓SYN → SYN-ACK → ACKUDP↓Fast↓No acknowledgmentsPorts↓Identify servicesHTTPS = 443HTTP = 80SSH = 22RDP = 3389
```

---