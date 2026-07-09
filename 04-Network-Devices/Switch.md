# Switch Fundamentals & CAM Table

## Overview

A switch is an intelligent networking device that connects multiple devices within the same network.

Switches operate at:

```
OSI Layer 2(Data Link Layer)
```

They use:

```
MAC Addresses
```

to forward data.

---

# Why is a Switch Called an Intelligent Device?

Unlike a hub, a switch does not send data to every device.

Instead:

```
Switch↓Sends data only to the destination device
```

This makes communication faster and more efficient.

---

# What is a MAC Address?

A MAC address is a unique physical identifier assigned to a device's network interface card (NIC).

Characteristics:

- Unique
- Permanent (usually)
- Layer 2 address

---

# What is a Frame?

A frame is the data unit used at:

```
OSI Layer 2
```

Switches forward frames.

---

# What is a Packet?

A packet is the data unit used at:

```
OSI Layer 3
```

Routers forward packets.

---

# What is a CAM Table?

CAM stands for:

```
Content Addressable Memory
```

A switch uses the CAM table to store:

```
MAC Address↓Switch Port
```

mapping information.

---

# How Does a CAM Table Work?

## Learning Process

Switches learn using:

```
Source MAC Address
```

Whenever a frame arrives, the switch stores:

```
Source MAC↓Incoming Port
```

inside the CAM table.

---

## Forwarding Process

Switches make forwarding decisions using:

```
Destination MAC Address
```

The switch checks its CAM table and forwards the frame to the correct port.

---

# Example

```
PC A↓Switch↓PC B
```

Flow:

```
Frame Arrives↓Read Source MAC↓Update CAM Table↓Read Destination MAC↓Forward to Correct Port
```

---

# Wireless Networks

Wireless Access Points behave more like hubs because they broadcast signals to connected devices.

Whenever possible:

> Use Ethernet cables.

Benefits:

- Better security
- Stable connection
- Fewer collisions

---

# Useful Cisco Command

Display MAC address table:

```
show mac-address-table
```

This command shows:

- Learned MAC addresses
- Associated switch ports

---

# Important Concepts to Remember

## CAM Table Population

Switches learn using:

```
Source MAC Address
```

---

## Forwarding Decisions

Switches forward using:

```
Destination MAC Address
```

---

# Troubleshooting Notes

### Scenario

> Devices connected to a switch cannot communicate.

Check:

1. Is the cable connected?
2. Is the device powered on?
3. Is the MAC address learned?
4. Is the correct switch port active?
5. Is the CAM table populated?

---

# Interview Questions

### Basic

1. What is a switch?
2. Why is a switch called an intelligent device?
3. Which OSI layer does a switch operate on?
4. What is a MAC address?
5. What is a CAM table?

### Intermediate

6. What is a frame?
7. Difference between a frame and a packet?
8. How does a switch learn devices?
9. How does a switch decide where to forward data?