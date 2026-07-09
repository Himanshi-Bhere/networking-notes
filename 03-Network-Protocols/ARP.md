# ARP (Address Resolution Protocol)

## What is ARP?

**ARP (Address Resolution Protocol)** converts a known **IP address** into an unknown **MAC address** inside a Local Area Network (LAN).

> Devices communicate using IP addresses at Layer 3, but actual communication on a LAN happens using MAC addresses at Layer 2.

---

## Why do we need ARP?

Suppose:

```
PC A wants to send data to PC BPC A knows:192.168.1.20PC A doesn't know:AA:BB:CC:DD:EE:FF
```

ARP helps find the MAC address.

Without ARP, devices inside a LAN cannot communicate.

---

# How ARP Works

## Step 1: ARP Request (Broadcast)

The source device sends:

```
Who has 192.168.1.20?Tell 192.168.1.10
```

Everyone on the network receives this message.

---

## Step 2: ARP Reply (Unicast)

Only the correct device responds.

```
192.168.1.20 is atAA:BB:CC:DD:EE:FF
```

---

## Step 3: ARP Cache

The source device stores the MAC address temporarily.

This avoids repeated ARP requests.

---

# ARP Communication Scenarios

## Host → Host

Two devices communicate within the same network.

```
Laptop ↔ Desktop
```

---

## Host → Gateway

When accessing another network (internet), ARP is used to find the router's MAC address.

```
Laptop → Router → Internet
```

---

# ARP Packet Structure

|Field|Purpose|
|---|---|
|Hardware Type|Network type (Ethernet = 1)|
|Protocol Type|IPv4 = 0800|
|Hardware Length|MAC length (6 bytes)|
|Protocol Length|IPv4 length (4 bytes)|
|Operation|Request (1) or Reply (2)|
|Source IP/MAC|Sender information|
|Target IP/MAC|Destination information|

---

# Dynamic vs Static ARP Entries

## Dynamic ARP

Characteristics:

- Automatically created
- Temporary
- Self-clearing

The operating system manages these entries.

---

## Static ARP

Characteristics:

- Added manually
- Permanent
- Does not expire

Used when devices communicate frequently.

---

# ICMP (Internet Control Message Protocol)

## What is ICMP?

ICMP is used for:

- Network diagnostics
- Error reporting
- Connectivity testing

---

## Why does Ping work?

Ping uses ICMP.

Flow:

```
Source↓ICMP Echo Request↓Destination↓ICMP Echo Reply↓Source
```

---

# IP Address vs MAC Address

|MAC Address|IP Address|
|---|---|
|Physical address|Logical address|
|Layer 2|Layer 3|
|Usually permanent|Can change|
|Identifies device hardware|Identifies device location|

---

# What Happens During Ping?

Suppose:

```
ping 192.168.1.20
```

The process:

```
Check ARP Table↓If MAC not found↓Send ARP Request↓Receive ARP Reply↓Send ICMP Echo Request↓Receive ICMP Echo Reply
```

---

# Linux Lab

## View ARP Table

```
arp -a
```

or

```
ip neigh
```

---

## Test Connectivity

```
ping google.com
```

---

## Observe Network Interface

```
ip addr
```

---

# Engineer Mindset 🧠

Scenario:

> Ping is not working.

Check:

1. Does the device have an IP?
2. Is ARP resolving?
3. Is the destination reachable?
4. Is ICMP blocked?
5. Is a firewall blocking traffic?

---

# Interview Questions

### Basic

1. What is ARP?
2. Why is ARP required?
3. What is an ARP Request?
4. What is an ARP Reply?
5. Why is ARP Request broadcast?
6. Why is ARP Reply unicast?
7. What is ICMP?

### Intermediate

8. Explain the complete flow of `ping`.
9. Difference between IP and MAC address.
10. What happens if a device doesn't know the destination MAC address?

---

# Revision Cheat Sheet

```
ARP = IP → MACARP 
Request = Broadcast
ARP Reply = Unicast
 ICMP = Diagnostics
 Ping = ICMP Echo Request + Echo Reply
 MAC = Layer 2IP = Layer 3
```