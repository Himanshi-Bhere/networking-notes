# Subnetting Fundamentals

## Overview

Subnetting is the process of dividing one large network into multiple smaller logical networks called **subnets**.

Subnetting helps improve:

- Network performance
- Security
- IP address management
- Scalability

---

# Why Do We Need Subnetting?

As organizations grow, a single large network becomes difficult to manage.

Subnetting helps to:

- Reduce network congestion
- Improve security
- Organize departments
- Efficiently use IP addresses

---

# Fundamental Concepts

## IP Address

An IP address is a unique numerical identifier assigned to every device on a network.

Example:

```
192.168.1.10
```

---

## Subnet Mask

A subnet mask divides an IP address into:

```
Network Portion+Host Portion
```

- Network Portion → Identifies the network
- Host Portion → Identifies the device

---

# IP Address Classes

## Class A

Used for very large networks.

Supports approximately:

```
16 million hosts
```

---

## Class B

Used for medium-sized organizations.

Supports approximately:

```
65,000 hosts
```

---

## Class C

Used for home and office networks.

Supports:

```
254 hosts
```

---

## Class D

Reserved for:

```
Multicast
```

Examples:

- Video streaming
- Conferencing

---

## Class E

Reserved for:

```
Research and experimental purposes
```

---

# Loopback Address

The range beginning with:

```
127.x.x.x
```

is reserved for internal communication.

Example:

```
127.0.0.1
```

Also called:

```
localhost
```

---

# Binary Fundamentals

Subnetting uses binary numbers.

8-bit chart:

```
128 | 64 | 32 | 16 | 8 | 4 | 2 | 1
```

Subnet masks use:

```
1 = Network bit0 = Host bit
```

---

# Host Calculation Formula

Formula:

```
2ⁿ - 2
```

Where:

```
n = Number of Host Bits
```

We subtract 2 because:

1. Network Address
2. Broadcast Address

cannot be assigned to devices.

---

# Network Address

The first address of a subnet.

It identifies the subnet itself.

Example:

```
192.168.1.0/24↓192.168.1.0
```

Cannot be assigned to a device.

---

# Broadcast Address

The last address in a subnet.

Used to communicate with all devices inside that subnet.

Example:

```
192.168.1.255
```

Cannot be assigned to a device.

---

# Host Addresses

Usable IP addresses assigned to devices.

Example:

For:

```
192.168.1.0/24
```

Usable range:

```
192.168.1.1↓192.168.1.254
```

---

# CIDR (Classless Inter-Domain Routing)

CIDR is the modern way of writing subnet masks.

Example:

```
192.168.1.0/24
```

`/24` means:

```
24 Network Bits
```

---

# /24 vs /25

|CIDR|Total Addresses|Usable Hosts|
|---|---|---|
|/24|256|254|
|/25|128|126|

A `/25` network is created by splitting a `/24` network into two smaller networks.

---

# Why Does Subnetting Matter?

## Security

Separate sensitive departments.

Example:

```
FinanceEngineeringGuest Network
```

---

## Reduce Congestion

Smaller networks reduce unnecessary traffic.

---

## Organize by Location

Different offices can have different subnets.

---

## Scalability

Networks can grow without redesigning the entire infrastructure.

---

# Classful vs Classless Networking

## Classful

- Fixed boundaries
- Inefficient
- Wastes IP addresses

---

## Classless (CIDR)

- Flexible
- Efficient
- Modern standard
- Reduces IP wastage

---

# Best Practices

### Document Everything

Record:

- IP ranges
- Subnet purposes
- Assigned devices

---

### Plan for Growth

Always leave room for future devices.

---

### Review Regularly

Audit networks periodically.

---

# Troubleshooting Notes

### Scenario

> Devices cannot communicate.

Check:

1. Are they in the same subnet?
2. Is the subnet mask correct?
3. Is the network address configured correctly?
4. Is the gateway reachable?

---

# Interview Questions

### Basic

1. What is subnetting?
2. Why do we subnet networks?
3. What is a subnet mask?
4. What is a network address?
5. What is a broadcast address?

### Intermediate

6. Why do we subtract 2 while calculating hosts?
7. Difference between `/24` and `/25`?
8. What is CIDR?
9. Difference between classful and classless networking?

---

# Quick Revision Cheat Sheet

```
Subnetting
↓
Divide one network into smaller networks
2ⁿ - 2
↓
Usable Hosts
Reserved:Network Address
Broadcast Address
CIDR
↓
Flexible subnetting/24 = 254 hosts/25 = 126 hosts
```