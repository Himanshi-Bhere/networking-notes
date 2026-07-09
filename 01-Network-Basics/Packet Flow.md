## Objective

Understand how a browser communicates with a web server over a network.

---

## Complete Packet Flow

```
User

↓

Browser Cache

↓

DNS Resolution

↓

ARP (Gateway MAC)

↓

Ethernet Frame

↓

Switch

↓

Router

↓

ISP

↓

Internet

↓

Destination Server

↓

TCP Handshake

↓

TLS Handshake

↓

HTTP Request

↓

HTTP Response

↓

Browser Renders Website
```

---

## Step Summary

|Step|Purpose|
|---|---|
|Browser Cache|Checks previously stored resources|
|DNS|Converts domain name to IP address|
|ARP|Finds the MAC address of the default gateway|
|Ethernet|Creates a frame for local delivery|
|Router|Forwards packets toward the destination|
|TCP|Establishes a reliable connection|
|TLS|Encrypts communication|
|HTTP|Requests and receives webpage content|

---

## Important Points

- DNS happens before TCP because the destination IP must be known first.
- ARP is only required within the local network.
- If the gateway MAC is already cached, no ARP request is sent.
- TCP provides reliable communication.
- TLS encrypts the connection.
- HTTP transfers the webpage data.

---

## Troubleshooting Order

When a website doesn't load, check in this order:

1. Internet connectivity
2. DNS resolution
3. ARP cache
4. Routing
5. TCP handshake
6. TLS handshake
7. HTTP response

---

## Interview Questions

1. What happens after typing a URL?
2. Why does DNS occur before TCP?
3. Why is ARP required?
4. Why doesn't ARP happen every time?
5. What is the role of TLS?
6. How would you troubleshoot a website that isn't loading?

---

## Key Commands

```
# View ARP cache
arp -a

# Test DNS resolution
nslookup google.com

# Check connectivity
ping google.com

# View routing table
route print      # Windows
ip route         # Linux
```

---

## Key Takeaways

- **DNS → IP Address**
- **ARP → MAC Address**
- **Ethernet → Local delivery**
- **Router → Network forwarding**
- **TCP → Reliable communication**
- **TLS → Encryption**
- **HTTP → Web data transfer**

---

## Memory Trick

```
Name → IP → MAC → Route → Connect → Encrypt → Request → Receive
```

or simply:

```
DNS
↓

ARP
↓

TCP
↓

TLS
↓

HTTP
```