# Ports, Sockets & Ephemeral Ports

## Overview

An IP address alone is not enough for communication because one device can run multiple applications simultaneously.

Ports were created to identify **which application should receive the data**.

---

# Why Do Ports Exist?

Suppose a laptop is running:

- Chrome
- WhatsApp
- Teams
- Spotify
- VS Code

All applications share the same IP address.

The operating system needs a way to distinguish between them.

This is where ports help.

---

# What is a Port?

A **port** is a **logical communication endpoint** that allows multiple applications and services to communicate over a network.

### Analogy

```
IP Address = BuildingPort = Apartment Number
```

Example:

```
192.168.1.10:443
```

- `192.168.1.10` → Device
- `443` → Specific service on that device

---

# Common Ports (Must Memorize)

|Port|Service|
|---|---|
|22|SSH|
|53|DNS|
|67/68|DHCP|
|80|HTTP|
|443|HTTPS|

> Focus on understanding these ports instead of memorizing dozens of them.

---

# What is a Socket?

A socket is:

```
IP Address + Port Number
```

Example:

```
192.168.1.10:54321
```

A complete connection consists of:

```
Client IPClient PortServer IPServer Port
```

Example:

```
192.168.1.10:54321↓142.250.xxx.xxx:443
```

This creates a unique communication session.

---

# What is an Ephemeral Port?

An **ephemeral port** is a temporary port automatically assigned by the operating system.

It is:

- Temporary
- Automatically created
- Removed after communication ends

Example:

```
Laptop192.168.1.10:54321↓Google142.xxx.xxx.xxx:443
```

Here:

```
54321
```

is an ephemeral port.

---

# Why Can One Laptop Open Multiple Websites?

Each connection uses a different ephemeral port.

Example:

### YouTube

```
192.168.1.10:54123↓youtube.com:443
```

### Gmail

```
192.168.1.10:54124↓gmail.com:443
```

### ChatGPT

```
192.168.1.10:54125↓chatgpt.com:443
```

This allows multiple applications to work simultaneously.

---

# Linux Lab

## Show Listening Ports

```
ss -tuln
```

---

## Show Active Connections

```
ss -tun
```

---

## Show Process Information

```
ss -tpn
```

---

# Troubleshooting Notes

### Scenario

> Website is not opening.

Check:

1. Is port 443 open?
2. Is DNS working?
3. Is the firewall blocking the connection?
4. Is the application running?
5. Is the TCP connection established?

---

# Interview Questions

### Basic

1. What is a port?
2. Why were ports created?
3. What is a socket?
4. What is an ephemeral port?

### Intermediate

5. Why can one laptop open multiple websites?
6. Difference between an IP address and a socket?
7. Explain:

```
192.168.1.10:54321↓142.250.xxx.xxx:443
```

---

# Quick Revision

```
Port = Logical communication endpoint
Socket = IP + Port
Ephemeral Port = Temporary OS-assigned port
HTTPS = 443
HTTP = 80
SSH = 22
DNS = 53
DHCP = 67/68
```