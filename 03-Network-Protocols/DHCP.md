
![[Pasted image 20260619164206.png]]


*# DHCP (Dynamic Host Configuration Protocol)

## What is DHCP?

**DHCP (Dynamic Host Configuration Protocol)** is a network management protocol that automatically assigns network configuration information to devices.

Instead of manually configuring every device, DHCP automates the process.

---

# Why Do We Need DHCP?

Every device needs the following to access a network:

- IP Address
- Subnet Mask
- Default Gateway
- DNS Server

Without DHCP, an administrator would have to manually configure every device.

DHCP saves time and reduces human errors.

---

# Static vs Dynamic IP Assignment

## Static Assignment

Administrator manually assigns:

- IP Address
- Subnet Mask
- Default Gateway
- DNS Server

### Drawbacks

- Time-consuming
- Difficult to manage large networks
- Risk of IP conflicts

---

## Dynamic Assignment (DHCP)

DHCP automatically assigns:

- IP Address
- Subnet Mask
- Default Gateway
- DNS Server

### Benefits

- Saves time
- Reduces manual work
- Prevents IP conflicts
- Easy to manage

---

# DHCP Scope

## What is a DHCP Scope?

A DHCP scope is a pool of available IP addresses that the DHCP server can assign.

Example:

```
DHCP Pool192.168.1.100↓192.168.1.200
```

Administrators can exclude certain IP addresses from this range.

---

# DHCP Lease

## What is a Lease?

DHCP assigns an IP address for a specific period of time.

This period is called a **Lease Duration**.

When the lease expires:

- Client renews the lease
- Or the IP returns to the available pool

---

# DORA Process (Must Memorize)

DHCP communication follows four steps.

```
D → DiscoverO → OfferR → RequestA → Acknowledge
```

---

## Step 1: Discover

Client broadcasts:

```
Is any DHCP server available?
```

---

## Step 2: Offer

DHCP server replies:

```
I can assign this IP address.
```

---

## Step 3: Request

Client responds:

```
I accept this IP address.
```

---

## Step 4: Acknowledge (ACK)

Server confirms:

```
You can now use this IP address.
```

Connection established.

---

# DHCP Ports

| Device      | UDP Port |
| ----------- | -------- |
| DHCP Server | 67       |
| DHCP Client | 68       |

> **Remember:** DHCP uses **UDP**, not TCP.

---

# DHCP Relay (Helper Agent)

## Why do we need DHCP Relay?

DHCP Discover is a broadcast message.

Broadcasts cannot cross routers.

If the DHCP server is on another subnet, we use a:

```
DHCP Relay
```

or

```
DHCP Helper Agent
```

to forward the request.

---

# Additional DHCP Options

DHCP can also provide:

- Time zone
- NTP server addresses
- Boot paths
- Static routes
- Interface MTU
- Device hostname

---

# What Happens When a Laptop Joins Wi-Fi?

```
Laptop↓DHCP Discover↓DHCP Offer↓DHCP Request↓DHCP ACK↓Laptop receives:IP AddressSubnet MaskDefault GatewayDNS Server
```

---

# Linux Lab

## Check Current IP Address

```
ip addr
```

---

## View Routing Table

```
ip route
```

---

## View DNS Configuration

```
cat /etc/resolv.conf
```

---

# Engineer Mindset 🧠

Scenario:

> Laptop connected to Wi-Fi but internet is not working.

Check:

1. Does the laptop have an IP address?
2. Is DHCP running?
3. Is the default gateway assigned?
4. Is DNS configured?
5. Can you ping the router?

---

# Interview Questions

### Basic

1. What is DHCP?
2. Why do we need DHCP?
3. What information does DHCP assign?
4. What is a DHCP Scope?
5. What is a DHCP Lease?

### Intermediate

6. Explain the DORA process.
7. Why does DHCP use UDP?
8. Why do we need DHCP Relay?
9. What happens when a laptop joins Wi-Fi?

---

# Revision Cheat Sheet

```
DHCP = Dynamic Host Configuration ProtocolAutomatically assigns:IP AddressSubnet MaskDefault GatewayDNS ServerDORA:D → DiscoverO → OfferR → RequestA → AcknowledgePorts:67 → Server68 → ClientDHCP uses UDP
```

> **Cloud Engineering Note:** DHCP is heavily used in enterprise networks, cloud environments, and Wi-Fi infrastructures. Understand DORA instead of memorizing definitions.