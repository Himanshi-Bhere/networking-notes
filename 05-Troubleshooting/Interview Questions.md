
---

# Section 1: Networking Fundamentals

## Q1. What is a network?

**Answer:**

A network is a collection of devices connected together to communicate and share resources such as files, internet access, and services.

Examples:

- Computers
    
- Laptops
    
- Servers
    
- Printers
    

Networks can be wired or wireless.

---

## Q2. What is LAN?

**Answer:**

LAN (Local Area Network) is a network that connects devices within a small geographical area such as a home, office, or school.

---

## Q3. What is WAN?

**Answer:**

WAN (Wide Area Network) connects multiple LANs over large geographical distances.

The Internet is the largest WAN.

---

## Q4. What is the difference between LAN and WAN?

| LAN                     | WAN                     |
| ----------------------- | ----------------------- |
| Small geographical area | Large geographical area |
| Faster                  | Comparatively slower    |
| Home/Office networks    | Internet                |

---

## Q5. What is a switch?

**Answer:**

A switch is a Layer 2 networking device that connects devices within the same network and forwards data using MAC addresses.

---

## Q6. What is a router?

**Answer:**

A router is a Layer 3 networking device that connects different networks and forwards packets using IP addresses.

---

## Q7. What is a firewall?

**Answer:**

A firewall is a security device that monitors, filters, and controls incoming and outgoing network traffic.

---

# Section 2: OSI Model

## Q8. Why was the OSI model created?

**Answer:**

OSI was created as a standard reference model to allow devices from different vendors to communicate and to simplify troubleshooting.

---

## Q9. Name all 7 OSI layers.

**Answer:**

```text
7 → Application

6 → Presentation

5 → Session

4 → Transport

3 → Network

2 → Data Link

1 → Physical
```

---

## Q10. Which layer uses IP addresses?

**Answer:**

Layer 3 (Network Layer).

---

## Q11. Which layer uses MAC addresses?

**Answer:**

Layer 2 (Data Link Layer).

---

## Q12. Difference between Layer 2 and Layer 3?

**Answer:**

Layer 2 uses MAC addresses for communication within a network.

Layer 3 uses IP addresses for communication between networks.

---

# Section 3: TCP/IP Model

## Q13. Which networking model is used by the Internet today?

**Answer:**

The TCP/IP model.

---

## Q14. Name all TCP/IP layers.

**Answer:**

```text
Application

↓

Transport

↓

Network

↓

Data Link

↓

Physical
```

---

# Section 4: IP Addressing

## Q15. What is an IP address?

**Answer:**

An IP address is a unique numerical identifier assigned to a device on a network.

It consists of:

- Network portion
    
- Host portion
    

---

## Q16. What is IPv4?

**Answer:**

IPv4 is a 32-bit address written in four octets separated by dots.

Example:

```text
192.168.1.10
```

---

## Q17. What is IPv6?

**Answer:**

IPv6 is a 128-bit address designed to overcome IPv4 address shortages.

---

## Q18. Difference between IPv4 and IPv6?

| IPv4              | IPv6               |
| ----------------- | ------------------ |
| 32 bits           | 128 bits           |
| Decimal           | Hexadecimal        |
| Limited addresses | Huge address space |

---

# Section 5: Public IP, Private IP & NAT

## Q19. What is a public IP address?

**Answer:**

A public IP is assigned by an ISP and is used to access the internet.

---

## Q20. What is a private IP address?

**Answer:**

A private IP is used inside local networks and cannot access the internet directly.

---

## Q21. What is NAT?

**Answer:**

NAT (Network Address Translation) converts private IP addresses into a public IP address.

---

## Q22. Why do we need NAT?

**Answer:**

NAT allows multiple devices to share one public IP address and conserves IPv4 addresses.

---

# Section 6: Subnetting & CIDR

## Q23. What is subnetting?

**Answer:**

Subnetting is the process of dividing one large network into smaller logical networks called subnets.

---

## Q24. Why do we subnet networks?

**Answer:**

To improve:

- Performance
    
- Security
    
- Management
    
- IP address utilization
    

---

## Q25. What is a network address?

**Answer:**

The first address of a subnet that identifies the network itself.

---

## Q26. What is a broadcast address?

**Answer:**

The last address of a subnet used to communicate with all devices.

---

## Q27. Why do we subtract 2 while calculating hosts?

**Answer:**

Because:

- One address is reserved for the Network ID.
    
- One address is reserved for the Broadcast Address.
    

---

## Q28. Difference between /24 and /25?

| CIDR | Total Addresses | Usable Hosts |
| ---- | --------------- | ------------ |
| /24  | 256             | 254          |
| /25  | 128             | 126          |

---

# Section 7: ARP

## Q29. What is ARP?

**Answer:**

ARP (Address Resolution Protocol) converts an IP address into a MAC address within a local network.

---

## Q30. Why is ARP needed?

**Answer:**

Because devices communicate using MAC addresses at Layer 2.

---

## Q31. What is an ARP Request?

**Answer:**

A broadcast message asking:

```text
Who has this IP address?
```

---

## Q32. What is an ARP Reply?

**Answer:**

A unicast response that contains the MAC address.

---

# Section 8: DHCP

## Q33. What is DHCP?

**Answer:**

DHCP automatically assigns:

- IP Address
    
- Subnet Mask
    
- Default Gateway
    
- DNS Server
    

---

## Q34. Why do we need DHCP?

**Answer:**

To automate network configuration and avoid manual assignments.

---

## Q35. Explain DORA.

**Answer:**

```text
D → Discover

O → Offer

R → Request

A → Acknowledge
```

---

## Q36. Which ports does DHCP use?

**Answer:**

```text
67 → Server

68 → Client
```

---

# Section 9: DNS

## Q37. What is DNS?

**Answer:**

DNS (Domain Name System) converts domain names into IP addresses.

---

## Q38. Why do we need DNS?

**Answer:**

Humans remember names better than IP addresses.

---

## Q39. What is DNS resolution?

**Answer:**

The process of converting a domain name into an IP address.

---

## Q40. What port does DNS use?

**Answer:**

```text
53
```

---

## Q41. What is an A Record?

**Answer:**

Maps a domain name to an IPv4 address.

---

## Q42. What is a CNAME Record?

**Answer:**

Creates an alias that points to another domain.

---

## Q43. What is an MX Record?

**Answer:**

Directs email traffic.

---

# Section 10: Ports & Sockets

## Q44. What is a port?

**Answer:**

A port is a logical communication endpoint used by applications.

---

## Q45. Why were ports created?

**Answer:**

To allow multiple applications to communicate simultaneously on one device.

---

## Q46. What is a socket?

**Answer:**

A socket is:

```text
IP Address + Port Number
```

---

## Q47. What is an ephemeral port?

**Answer:**

A temporary port automatically assigned by the operating system.

---

# Section 11: TCP & UDP

## Q48. What is TCP?

**Answer:**

TCP is a reliable, connection-oriented protocol.

---

## Q49. What is UDP?

**Answer:**

UDP is a fast, connectionless protocol.

---

## Q50. Difference between TCP and UDP?

| TCP                 | UDP            |
| ------------------- | -------------- |
| Reliable            | Fast           |
| Connection-oriented | Connectionless |
| Ordered delivery    | No guarantee   |

---

## Q51. Explain the TCP Three-Way Handshake.

**Answer:**

```text
SYN

↓

SYN-ACK

↓

ACK
```

Connection established.

---

# Section 12: HTTP, HTTPS & TLS

## Q52. What is HTTP?

**Answer:**

HTTP is an Application Layer protocol used for communication between browsers and web servers.

---

## Q53. What is HTTPS?

**Answer:**

HTTPS = HTTP + TLS

It encrypts communication.

---

## Q54. What is TLS?

**Answer:**

TLS (Transport Layer Security) secures communication.

It provides:

- Encryption
    
- Authentication
    
- Integrity
    

---

## Q55. Difference between HTTP and HTTPS?

| HTTP       | HTTPS     |
| ---------- | --------- |
| Not secure | Secure    |
| Plain text | Encrypted |
| Port 80    | Port 443  |

---

# Section 13: Master Fresher Question ⭐

## Q56. What happens when you type google.com and press Enter?

**Answer:**

```text
Browser

↓

Browser Cache

↓

DNS Resolution

↓

ARP Resolution

↓

Routing

↓

TCP Handshake

↓

TLS Handshake

↓

HTTP Request

↓

Server Response

↓

Browser Render
```

---

# Section 14: Master Troubleshooting Question ⭐⭐⭐⭐⭐

## Q57. A website is not opening. How would you troubleshoot?

**Answer:**

1. Check network connectivity.
    
2. Check IP address.
    
3. Check DNS resolution.
    
4. Check network reachability.
    
5. Check HTTP/HTTPS ports.
    
6. Check firewall/security groups.
    
7. Check whether the application is running.
    

---

