# Network Fundamentals

## What is a Network?

A network is a collection of devices connected together to communicate and share resources.

Examples of devices:

- Computers
- Laptops
- Printers
- Servers

Networks can be:

- Wired
- Wireless

---

# Basic Network Components

A typical network setup:

```
PC↓Switch↓Router↓Firewall↓Modem↓ISP↓Internet
```

---

# What is LAN?

LAN stands for:

```
Local Area Network
```

A LAN is a network within a small geographical area.

Examples:

- Home
- Office
- School

Devices inside a LAN communicate with each other.

---

# What is WAN?

WAN stands for:

```
Wide Area Network
```

A WAN connects multiple LANs together over large distances.

Example:

```
Home Network↓Internet↓Company Network
```

---

# What is a Switch?

A switch connects multiple devices inside the same network.

Responsibilities:

- Connect devices
- Forward data within a LAN
- Operates at Layer 2

---

# What is a Router?

A router connects different networks together.

Responsibilities:

- Connect LANs
- Route traffic
- Operates at Layer 3

---

# What is a Firewall?

A firewall protects a network from unauthorized access.

Responsibilities:

- Filters traffic
- Blocks malicious packets
- Protects against attacks

Think of it as a security guard for the network.

---

# Network Flow Example

```
Laptop↓Switch↓Router↓Firewall↓Modem↓Internet
```

Each device has a specific responsibility.

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

## Test Internet Connectivity

```
ping google.com
```

---

# Troubleshooting Notes

## Scenario

> Internet is not working.

Check:

1. Is the device connected to the switch?
2. Is the router working?
3. Is the firewall blocking traffic?
4. Is the modem connected?
5. Is the ISP connection active?

---

# Interview Questions

### Basic

1. What is a network?
2. Difference between LAN and WAN?
3. What is a switch?
4. What is a router?
5. What is a firewall?

### Intermediate

6. Explain the flow from a laptop to the internet.
7. Why do we need a firewall?
8. Why do we need a router?

---

# Quick Revision Cheat Sheet

```
Network↓Connect DevicesLAN↓Small NetworkWAN↓Connects Multiple NetworksSwitch↓Connect DevicesLayer 2Router↓Connect NetworksLayer 3Firewall↓Protect NetworkInternet Flow:PC↓Switch↓Router↓Firewall↓Modem↓Internet
```