![[Pasted image 20260605092754.png]]
#![[Pasted image 20260605091802.png]]
# IP Address Fundamentals

## What is an IP Address?

An **IP Address (Internet Protocol Address)** is a unique numeric identifier assigned to a device on a network.

Think of it as a **home address for a device**.

Every IP address has two parts:

```
Network Portion+Host Portion
```

- **Network Portion:** Identifies the network.
- **Host Portion:** Identifies a specific device inside that network.

---

# IPv4 Addressing

## What is IPv4?

IPv4 is the fourth version of the Internet Protocol.

### Specifications

- 32-bit address
- Divided into 4 octets
- Each octet = 8 bits
- Values range from 0 to 255

Example:

```
192.168.1.10
```

Structure:

```
192 . 168 . 1 . 108 bits 8 bits 8 bits 8 bits
```

---

# Subnet Mask

## What is a Subnet Mask?

A subnet mask helps determine:

```
Which part = NetworkWhich part = Host
```

---

## Default Subnet Masks

### Class A

```
255.0.0.0/8
```

- First octet = Network
- Remaining = Host

---

### Class B

```
255.255.0.0/16
```

- First 2 octets = Network
- Remaining = Host

---

### Class C

```
255.255.255.0/24
```

- First 3 octets = Network
- Last octet = Host

---

# Slash Notation (CIDR)

CIDR is a shorthand way of writing subnet masks.

Examples:

```
255.0.0.0     → /8255.255.0.0   → /16255.255.255.0 → /24
```

---

# Same Network vs Different Network

## Same Network

If two devices have the same network portion:

```
PC A ↔ Switch ↔ PC B
```

They can communicate directly.

---

## Different Network

If network portions are different:

```
PC A ↔ Router ↔ PC B
```

A router is required.

---

# Reserved Addresses

Every network reserves two addresses.

## Network ID

First address.

Cannot be assigned.

---

## Broadcast Address

Last address.

Cannot be assigned.

---

# Binary Conversion

Computers understand only:

```
0 and 1
```

8-bit chart:

```
128 | 64 | 32 | 16 | 8 | 4 | 2 | 1
```

Example:

```
192128 + 64= 11000000
```

---

# IPv6 Addressing

## What is IPv6?

IPv6 was created to overcome IPv4 limitations.

Specifications:

- 128-bit address
- Uses hexadecimal values
- Contains numbers and letters
- Divided into 8 groups

Example:

```
2001:0db8:85a3:0000:0000:8a2e:0370:7334
```

---

# Hexadecimal Basics

Each hexadecimal character = 4 bits

```
8 | 4 | 2 | 1
```

Values:

```
10 = A11 = B12 = C13 = D14 = E15 = F
```

---

# IPv4 vs IPv6

| IPv4              | IPv6               |
| ----------------- | ------------------ |
| 32 bits           | 128 bits           |
| Decimal           | Hexadecimal        |
| 4 octets          | 8 groups           |
| Limited addresses | Huge address space |

---

# Linux Lab

## Check IP Address

```
ip addr
```

---

## Display Routing Table

```
ip route
```

---

## Check Connectivity

```
ping google.com
```

---

# Troubleshooting Notes

### Scenario

> Two devices cannot communicate.

Check:

1. Are they in the same network?
2. Is the subnet mask correct?
3. Does the device have an IP address?
4. Is the router configured?

---

# Interview Questions

### Basic

1. What is an IP address?
2. What are the two parts of an IP address?
3. What is IPv4?
4. What is IPv6?
5. What is a subnet mask?

### Intermediate

6. Difference between IPv4 and IPv6?
7. When do we need a router?
8. What is CIDR notation?
9. Why are two addresses reserved?

---

# Revision Cheat Sheet

```
IP Address
↓
Network Portion+Host Portion
IPv4 = 32 bits
IPv6 = 128 bits
Subnet Masks:255.0.0.0 = /8255.255.0.0 = /16255.255.255.0 = /24
Reserved:Network ID
 Broadcast Address
```