


 Routing, Default Gateway & Routing Tables

## Overview

Communication inside the same network is handled directly by devices using switches.

However, when devices need to communicate with a **different network**, they require a **router**.

Routing is the process of forwarding packets from one network to another using IP addresses.

---

# Why Was a Router Created?

Consider two different networks:

```text
Network A
192.168.1.0/24

Network B
192.168.2.0/24
```

If:

```text
PC A → 192.168.1.10
PC B → 192.168.2.10
```

Both devices belong to different networks.

Without a router:

```text
PC A ❌ PC B
```

They cannot communicate because they don't know how to reach the other network.

A router provides the path between different networks.

---

# What is a Router?

A **Router** is a **Layer 3 (Network Layer)** device that forwards packets between different networks using **IP addresses**.

### Responsibilities

- Connect different networks
    
- Forward IP packets
    
- Select the best path using a routing table
    
- Act as the default gateway for devices
    

---

# Same Network vs Different Network

## Same Network

Example:

```text
PC A → 192.168.1.10
PC B → 192.168.1.20
```

Communication:

```text
PC A
   │
Switch
   │
PC B
```

No router is required.

---

## Different Networks

Example:

```text
PC A → 192.168.1.10

PC B → 192.168.2.10
```

Communication:

```text
PC A
   │
Switch
   │
Router
   │
Switch
   │
PC B
```

A router is mandatory.

---

# What is a Default Gateway?

A **Default Gateway** is the router that a device uses when the destination network is outside its local network.

Think of it like this:

```text
Your House
     │
Local Road
     │
Highway
     │
Destination
```

The **default gateway** is your **first exit point** from the local network.

---

## Example

Laptop configuration:

```text
IP Address

192.168.1.10

Gateway

192.168.1.1
```

Suppose you want to open Google.

Google's IP:

```text
8.8.8.8
```

Your laptop checks:

> Is `8.8.8.8` inside my network?

Answer:

```text
No
```

It sends the packet to:

```text
192.168.1.1
```

which is the default gateway.

The router then forwards the packet toward the internet.

---

# What is a Routing Table?

A **Routing Table** is a list of known networks and the paths used to reach them.

Think of it as **Google Maps for a router**.

Each entry tells the router:

- Destination network
    
- Next hop
    
- Outgoing interface
    

---

## Example Routing Table Entry

```text
Destination

0.0.0.0/0

↓

Next Hop

192.168.1.1
```

Meaning:

> Any traffic for an unknown destination should be sent to the default gateway.

---

# Real Packet Flow

When opening:

```text
google.com
```

The packet travels as follows:

```text
Laptop
192.168.1.10

↓

Default Gateway
192.168.1.1

↓

ISP Router

↓

Internet

↓

Google Server
```

Each router along the way checks its routing table and forwards the packet to the next appropriate destination.

---

# Linux Lab

## Lab 1 – View Routing Table

Command:

```bash
ip route
```

Example output:

```text
default via 192.168.1.1 dev wlan0
192.168.1.0/24 dev wlan0
```

Observe:

- Default gateway
    
- Connected networks
    
- Network interfaces
    

---

## Lab 2 – View Network Interface

Command:

```bash
ip a
```

Observe:

- IP Address
    
- Interface name (e.g., `eth0`, `wlan0`)
    
- Interface status
    

---

## Lab 3 – Trace Packet Journey

If `traceroute` is not installed:

```bash
sudo apt install traceroute
```

Run:

```bash
traceroute google.com
```

Example:

```text
Hop 1 → Home Router

Hop 2 → ISP Router

Hop 3 → ISP Core Router

...

Final Hop → Google
```

This command shows every router the packet passes through.

---

# Troubleshooting Notes

## Scenario

> User reports: "Internet is not working."

Follow this sequence:

### Step 1 – Verify IP Address

```bash
ip a
```

Check if the system has a valid IP address.

---

### Step 2 – Test Gateway Connectivity

```bash
ping 192.168.1.1
```

If this fails:

- Router may be down
    
- Cable/Wi-Fi issue
    
- Incorrect gateway
    

---

### Step 3 – Test Internet Reachability

```bash
ping 8.8.8.8
```

If successful:

- Internet connectivity exists
    
- DNS may be the issue
    

---

### Step 4 – Verify DNS Resolution

```bash
nslookup google.com
```

or

```bash
dig google.com
```

If domain resolution fails:

- DNS server issue
    
- Incorrect DNS configuration
    

---

### Step 5 – Trace the Route

```bash
traceroute google.com
```

Use this to identify where the connection is failing.

---

# Real-World Projects

## Project 1 – Enterprise Office Network

### Objective

Design an office network for 50 employees.

### VLANs

- HR
    
- IT
    
- Finance
    
- Guest
    
- Server
    

### Technologies

- DHCP
    
- DNS
    
- Inter-VLAN Routing
    
- NAT
    
- SSH
    

### Tools

- Cisco Packet Tracer
    
- Ubuntu VM
    

---

## Project 2 – Multi-Branch Company

### Branches

- Mumbai
    
- Pune
    
- Bangalore
    

### Technologies

- OSPF
    
- VPN
    
- Redundancy
    

---

## Project 3 – Mini Data Center

Architecture:

```text
Internet

↓

Firewall

↓

Load Balancer

↓

Web Server

↓

Application Server

↓

Database Server
```

### Technologies

- DNS
    
- NAT
    
- VLAN
    
- Monitoring
    

---

# Interview Questions & Answers

## Q1. What is a router?

**Answer:**

A router is a Layer 3 networking device that forwards packets between different networks using IP addresses. It determines the best path for data using a routing table.

---

## Q2. Why was a router created?

**Answer:**

A router was created to enable communication between different networks. Devices on separate networks cannot communicate directly because they have different network addresses. The router forwards packets between those networks.

---

## Q3. What is a default gateway?

**Answer:**

A default gateway is the router that a device uses to send traffic destined for networks outside its local network. It acts as the first exit point from the local network.

---

## Q4. What is a routing table?

**Answer:**

A routing table is a database maintained by a router or host that contains information about destination networks, next-hop addresses, and interfaces used to forward packets.

---

## Q5. Why can't two different networks communicate without a router?

**Answer:**

Devices only know how to communicate within their own network. When the destination belongs to a different network, a router is required to forward packets between the two networks.

---

## Q6. Explain this flow:

```text
192.168.1.10

↓

192.168.1.1

↓

8.8.8.8
```

**Answer:**

- `192.168.1.10` is the laptop's IP address.
    
- `192.168.1.1` is the default gateway (router).
    
- `8.8.8.8` is the destination (Google DNS).
    

Since the destination is outside the local network, the laptop sends the packet to the default gateway. The router then forwards it toward Google.

---

## Q7. If a user cannot access Google, what are the first five checks?

**Answer:**

1. Verify the device has a valid IP address using `ip a`.
    
2. Check connectivity to the default gateway using `ping <gateway-ip>`.
    
3. Test internet connectivity using `ping 8.8.8.8`.
    
4. Verify DNS resolution using `nslookup google.com` or `dig google.com`.
    
5. Trace the route using `traceroute google.com` to locate where the connection fails.
    

---

## Q8. Which Linux commands should every Network/Cloud Engineer know for routing?

|Command|Purpose|
|---|---|
|`ip a`|Display network interfaces and IP addresses|
|`ip route`|Display the routing table|
|`ping`|Test connectivity to a host|
|`traceroute`|Show the packet's path through the network|
|`nslookup`|Test DNS resolution|
|`dig`|Query detailed DNS information|

---

# Quick Revision Cheat Sheet

```text
Router

↓

Layer 3 Device

↓

Uses IP Address

Default Gateway

↓

First exit point from the local network

Routing Table

↓

Destination
Next Hop
Interface

Useful Commands

ip a
ip route
ping
traceroute
nslookup
dig

Internet Flow

Laptop
↓

Gateway
↓

ISP Router
↓

Internet
↓

Destination
```

> **Cloud Engineering Note:** Routing and default gateways are core concepts in enterprise networking and cloud platforms such as AWS, Azure, and Google Cloud. Services like VPC routing tables, Internet Gateways, NAT Gateways, VPN Gateways, and Transit Gateways all build on these fundamentals. Understanding routing at this level will make cloud networking concepts much easier to learn later.