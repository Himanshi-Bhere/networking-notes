# Public IP, Private IP & NAT

## What is an IP Address?

An IP address is a unique numeric identifier assigned to a device on a network.

Every device requires an IP address to communicate.

There are two types:

- Public IP
- Private IP

---

# Public IP Address

A **Public IP** is assigned by your ISP.

Characteristics:

- Globally unique
- Publicly accessible
- Used to access the internet

Without a public IP:

```
Internet access = Impossible
```

---

# Why Do We Have IPv4 Shortage?

Early engineers created approximately:

```
4 billion
```

IPv4 addresses.

Due to the growth of the internet, this became insufficient.

To solve this:

- Private IPs were introduced
- IPv6 was created

---

# Private IP Address

Private IPs are used inside local networks.

Examples:

```
HomeOfficeSchool
```

Characteristics:

- Internal use only
- Cannot access the internet directly
- Assigned by DHCP

---

# Why Do We Use Private IPs?

Without private IPs:

Every device would require its own public IP.

This would be:

- Expensive
- Inefficient
- Unsustainable

---

# What is NAT?

**NAT (Network Address Translation)** converts private IP addresses into a public IP address.

The router performs this translation.

---

# How NAT Works

## Outbound Traffic

```
Laptop↓Private IP↓Router (NAT)↓Public IP↓Internet
```

---

## Inbound Traffic

```
Internet↓Public IP↓Router (NAT)↓Private IP↓Correct Device
```

---

# Private IP Ranges

## Class A

```
10.x.x.x
```

Large organizations.

---

## Class B

```
172.x.x.x
```

Medium organizations.

---

## Class C

```
192.168.x.x
```

Small organizations and homes.

Most common.

---

# Static vs Dynamic IP

## Static IP

Characteristics:

- Fixed
- Manually assigned
- Does not change

Used for:

- Servers
- Hosting applications
- Remote access

---

## Dynamic IP

Characteristics:

- Automatically assigned
- Managed by DHCP
- Can change

Used for:

- Home users
- General devices

---

# Linux Lab

## Find Private IP

```
ip addr
```

---

## Display Network Interfaces

```
ifconfig
```

---

# Troubleshooting Notes

### Scenario

> Device has Wi-Fi but internet is not working.

Check:

1. Does it have a private IP?
2. Is DHCP working?
3. Is NAT working?
4. Is the router connected to the ISP?

---

# Interview Questions

### Basic

1. What is a public IP?
2. What is a private IP?
3. Why do we need NAT?
4. Why was IPv6 introduced?

### Intermediate

5. Difference between static and dynamic IP?
6. Who assigns public IP addresses?
7. Who assigns private IP addresses?

---

# Quick Revision

```
Public IP↓Assigned by ISP↓Internet AccessPrivate IP↓Assigned by DHCP↓Local NetworkNAT↓Private IP ↔ Public IP
```