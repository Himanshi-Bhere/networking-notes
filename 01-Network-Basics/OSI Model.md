![[Screenshot (649).png]]
![[Pasted image 20260603103442.png]]

 # OSI Model (Open Systems Interconnection)

## Why was OSI created?

OSI was created as a standard reference model to:

- Help different vendors communicate
- Standardize networking
- Simplify troubleshooting

Engineers still use it daily.

Example:

> "This is a Layer 7 issue."

---

# 7 Layers of OSI

```
7 → Application6 → Presentation5 → Session4 → Transport3 → Network2 → Data Link1 → Physical
```

### OSI Diagram

```text
Application
Presentation
Session
Transport
Network
Data Link
Physical
```

---

# Easy Mnemonics

### Top → Bottom

```
All People Seem To Need Data Processing
```

### Bottom → Top

```
Please Do Not Throw Sausage Pizza Away
```

---

# Layer 7: Application

## Purpose

User-facing applications.

Examples:

- HTTP
- HTTPS
- DNS

Example:

```
Browser sends GET request
```

---

# Layer 6: Presentation

## Purpose

Acts as a translator.

Responsibilities:

- Data formatting
- Encryption
- Compression

Examples:

- SSL
- TLS
- ASCII
- Base64

---

# Layer 5: Session

## Purpose

Manages communication sessions.

Example:

```
HTTP Cookies
```

Keeps users logged in.

---

# Layer 4: Transport

## Purpose

Service-to-service communication.

Protocols:

```
TCPUDP
```

### TCP

Reliable.

### UDP

Fast.

Uses:

```
Ports
```

Examples:

```
80 → HTTP443 → HTTPS
```

---

# Layer 3: Network

## Purpose

End-to-end communication.

Uses:

```
IP Address
```

Device:

```
Router
```

---

# Layer 2: Data Link

## Purpose

Hop-to-hop communication.

Uses:

```
MAC Address
```

Device:

```
Switch
```

Creates:

```
Frames
```

---

# Layer 1: Physical

## Purpose

Transmits bits.

Examples:

- Ethernet cables
- Fiber optics
- Wi-Fi signals

Transfers:

```
0 and 1
```

---

# Encapsulation

Data moves down the layers.

```
Application Data↓Segment↓Packet↓Frame↓Bits
```

---

# De-encapsulation

Receiver removes headers layer by layer.

```
Bits↓Frame↓Packet↓Segment↓Application Data
```

---

# Website Request Example

When opening:

```
https://google.com
```

Flow:

```
Browser↓DNS Resolution↓TCP Handshake↓TLS Handshake↓HTTP Request↓Encapsulation↓Server Response↓Browser Render
```

---

# Layer Devices

| Layer   | Device        |
| ------- | ------------- |
| Layer 1 | Hub, Repeater |
| Layer 2 | Switch        |
| Layer 3 | Router        |

---

# Protocol Mapping

| Layer        | Protocol           |
| ------------ | ------------------ |
| Application  | HTTP, HTTPS, DNS   |
| Presentation | SSL/TLS            |
| Session      | Session Management |
| Transport    | TCP, UDP           |
| Network      | IP                 |
| Data Link    | MAC                |
| Physical     | Cables             |

---

# Linux Lab

## Check Network Interfaces

```
ip addr
```

---

## View Routing Table

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

Check:

1. Is DNS working?
2. Is TCP working?
3. Is HTTPS/TLS working?
4. Is routing working?
5. Is the server reachable?

---

# Interview Questions

### Basic

1. What is OSI?
2. Why was OSI created?
3. Explain all 7 layers.
4. Difference between Layer 2 and Layer 3?
5. Difference between TCP and UDP?

### Intermediate

6. What is encapsulation?
7. What is de-encapsulation?
8. Which devices operate at Layer 2 and Layer 3?
9. Explain what happens when you open a website.

---

# Revision Cheat Sheet

```
7 → Application
6 → Presentation
5 → Session
4 → Transport
3 → Network
2 → Data Link
1 → Physical
TCP → Reliable
UDP → Fast
Switch → Layer 2
Router → Layer 3
Encapsulation:Data
↓Segment
↓
Packet
↓
Frame
↓
Bits
```

> **Cloud Engineering Note:** OSI is the universal troubleshooting language. Even though modern networks use TCP/IP, cloud engineers still think in OSI layers when diagnosing issues.