# Switches, Routers, Gateway & Routing Fundamentals

## Switch vs Router

### Switch

A switch connects devices within the same network.

Operates at:

```
OSI Layer 2
```

Uses:

```
MAC Address
```

---

### Router

A router connects different networks.

Operates at:

```
OSI Layer 3
```

Uses:

```
IP Address
```

---

# What Defines a Network?

A network is defined by a specific range of IP addresses.

If a destination belongs to another network:

```
Router is required
```

---

# What is a Default Gateway?

A default gateway is the device that acts as an exit point for traffic leaving the local network.

Usually:

```
Router
```

---

# ARP (Address Resolution Protocol)

ARP converts:

```
IP Address↓MAC Address
```

ARP is required for Layer 2 communication.

---

# Routing Traffic

When communicating outside the local network:

```
Host↓Gateway (Router)↓Routing Table↓Destination Network
```

Routers use routing tables to determine the path.

---

# DNS Reminder

DNS converts:

```
Domain Name↓IP Address
```

Example:

```
google.com↓142.250.xxx.xxx
```

---

# Practical Commands

## Cisco Router Routing Table

```
show ip route
```

Displays all known networks.

---

# Packet Tracer

Simulation Mode can be used to visualize:

- Frames
- Packets
- Data movement
- Routing process

---

# Troubleshooting Notes

### Scenario

> Cannot access another network.

Check:

1. Is the gateway configured?
2. Is the router working?
3. Is DNS working?
4. Is the route available?

---

# Interview Questions

### Basic

1. Difference between a switch and a router?
2. What is a default gateway?
3. What is ARP?
4. Why do we need routing?

### Intermediate

5. What happens when a device communicates with another network?
6. What does a router use to forward packets?
7. Why is DNS required?

---

# Quick Revision

```
Switch↓Layer 2↓MAC AddressRouter↓Layer 3↓IP AddressGateway↓Exit point of networkARP↓IP → MACDNS↓Domain → IP
```