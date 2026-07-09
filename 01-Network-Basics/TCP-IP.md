![[tcp.png]] 
# TCP/IP Model Fundamentals

## Overview

In the early days of computing, devices from different companies could not communicate with each other because they used incompatible networking systems.

To solve this problem, engineers created standardized networking models.

Today, the internet uses the **TCP/IP model**.

---

# What is TCP/IP?

TCP/IP is the networking model used by the internet.

It organizes communication into layers.

Each layer has a specific responsibility.

---

# TCP/IP Layers

```
Application↓Transport↓Network↓Data Link↓Physical
```

---

# Layer 5: Application Layer

## Purpose

Provides services directly to applications used by users.

Example:

```
HTTPHTTPS
```

Used for:

- Web browsing
- User requests

---

# Layer 4: Transport Layer

## Purpose

Controls how data is delivered.

Protocols:

```
TCPUDP
```

Responsibilities:

- Reliable communication
- Port management

---

# Layer 3: Network Layer

## Purpose

Determines where data should go.

Uses:

```
IP Address
```

Device:

```
Router
```

---

# Layer 2: Data Link Layer

## Purpose

Moves data inside the local network.

Uses:

```
MAC Address
```

Device:

```
Switch
```

---

# Layer 1: Physical Layer

## Purpose

Transfers data physically.

Examples:

- Ethernet cables
- Wi-Fi
- Electrical signals

Transmits:

```
0 and 1
```

---

# Real Example: Opening YouTube

When opening YouTube:

## Application Layer

Browser creates a request.

↓

## Transport Layer

TCP ensures reliable delivery.

↓

## Network Layer

IP addresses are used.

↓

## Data Link Layer

MAC addresses are used.

↓

## Physical Layer

Bits travel through cables or Wi-Fi.

---

# Data Flow

```
Browser Request↓TCP↓IP Address↓MAC Address↓Bits on Wire
```

---

# Why is TCP/IP Important?

TCP/IP allows devices from different manufacturers to communicate using common standards.

Examples:

- Laptop ↔ Server
- Phone ↔ Website
- Raspberry Pi ↔ Cloud Server

---

# Linux Lab

## Display Network Interfaces

```
ip addr
```

---

## Display Routing Table

```
ip route
```

---

## Test Connectivity

```
ping google.com
```

---

# Troubleshooting Notes

### Scenario

> Website is not opening.

Check layer by layer:

1. Is the application working?
2. Is TCP established?
3. Is the IP reachable?
4. Is the MAC address resolved?
5. Is the physical connection available?

---

# Interview Questions

### Basic

1. Why was TCP/IP created?
2. What are the TCP/IP layers?
3. Which model is used by the internet today?
4. Which layer uses IP addresses?
5. Which layer uses MAC addresses?

### Intermediate

6. Explain the flow when opening YouTube.
7. Difference between TCP/IP and OSI?
8. Why do we use networking models?

---

# Quick Revision Cheat Sheet

```
TCP/IP Model↓Application↓Transport↓Network↓Data Link↓PhysicalApplication → HTTPTransport → TCP/UDPNetwork → IPData Link → MACPhysical → Cables/Wi-Fi
```