# CIDR (Classless Inter-Domain Routing)

## Why is Networking Important in Cloud?

Cloud providers like:

- AWS
- Azure
- Google Cloud

use networking to divide resources into:

- Public subnets
- Private subnets

This helps:

- Improve security
- Control traffic flow
- Isolate sensitive resources

Modern cloud infrastructure uses **CIDR**.

---

# What is CIDR?

CIDR is a method for allocating IP addresses without using traditional classes (A, B, C).

Example:

```
10.10.10.0/24
```

---

# IPv4 Basics

IPv4 consists of:

```
32 bits
```

Divided into:

```
4 Octets8 bits + 8 bits + 8 bits + 8 bits
```

Example:

```
10.10.10.0
```

---

# Understanding CIDR Notation

Example:

```
10.10.10.0/24
```

### Network Bits

```
24 bits
```

### Host Bits

```
32 - 24 = 8 bits
```

---

# Host Calculation Formula

```
2^(Host Bits)
```

Example:

```
2^8 = 256
```

Total addresses:

```
256
```

---

# Reserved Addresses

Every network reserves two addresses.

## Network ID

First address

```
10.10.10.0
```

Cannot be assigned.

---

## Broadcast Address

Last address

```
10.10.10.255
```

Cannot be assigned.

---

## Usable Hosts

```
256 - 2 = 254
```

Usable IPs:

```
10.10.10.1to10.10.10.254
```

---

# Why do we need Subnetting?

Suppose a company has:

```
Web ApplicationDatabaseFirewallServers
```

We don't want everything in one network.

Instead:

```
Internet↓Public Subnet(Web Server)↓Private Subnet(Database)
```

This improves security.

---

# Choosing the Correct CIDR Block

Suppose we need:

```
200 devices
```

Compare:

|CIDR|Total IPs|Suitable?|
|---|---|---|
|/25|128|❌ Too small|
|/24|256|✅ Perfect|
|/23|512|❌ Wasteful|

Always choose the closest size.

---

# How Subnetting Works

Golden Rule:

> Never modify the Network Bits.

Example:

```
10.10.0.0/24
```

Split into two networks.

Reserve the 25th bit.

---

## Subnet 1

25th bit = 0

Range:

```
10.10.0.0to10.10.0.127
```

---

## Subnet 2

25th bit = 1

Range:

```
10.10.0.128to10.10.0.255
```

Now we have two separate networks.

---

# Router & Subnet Mask

The router uses:

```
IP Address+Subnet Mask
```

It performs a logical AND operation.

This helps determine which subnet the packet belongs to.

---

# Linux Lab

## Display IP Address

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

# Engineer Mindset 🧠

Scenario:

> Users can access the website but not the database.

Think:

1. Is the database inside a private subnet?
2. Are security groups configured correctly?
3. Is the route table configured?
4. Is the subnet mask correct?

---

# Interview Questions

### Basic

1. What is CIDR?
2. Why was CIDR introduced?
3. What is an IPv4 address?
4. What is CIDR notation?
5. Difference between Network Bits and Host Bits?

### Intermediate

6. How many hosts does `/24` support?
7. Why are two addresses reserved?
8. Explain subnetting.
9. Why do cloud providers use subnetting?
10. Explain public vs private subnets.

---

# Revision Cheat Sheet

```
IPv4 = 32 bits4 OctetsCIDR = Flexible IP allocation/24Network Bits = 24Host Bits = 82^8 = 256Usable Hosts = 254Reserved:Network IDBroadcast AddressSubnetting:Never modify Network BitsPublic Subnet → Internet-facingPrivate Subnet → Internal resources
```

> **Cloud Engineering Note:** CIDR and subnetting are foundational topics for AWS VPC, Azure VNets, Kubernetes networking, and Cloud Engineering interviews. Focus on understanding the logic instead of memorizing numbers.