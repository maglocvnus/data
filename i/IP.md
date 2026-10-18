# Internet Protocol

The `Internet Protocol` (IP) is a set of rules governing how data should be transferred across the internet from one computer to another.

A best effort delivery protocol – it attempts to deliver each packet, but makes no promise of success (cf. TCP)



## IP addresses

Every computer on the internet has a unique IP address.

Examples:
- `192.168.1.25`
- `8.8.8.8` (a public IP address used by Googles DNS service)

IPv4 – 32-bit addresses

IPv6 – 128-bit addresses, eg. `2001:db8::1`

IPv4:

typically represented as four octets separated by periods. Each octet represented in base-10 ie. 0 to 255.

ie. dotted decimal notation, for readability

IPv6:

- colon separators, dividing four hexadecimal numbers



## IP packets

header – source address, destination address, other control info

payload

Maximum size of an IP packet is 65,535 bytes.

However, most are much smaller since the maximum size of a ethernet frame is 1500 bytes.

The standard header size for an IPv4 packet is 20 bytes.

- **version** (8 bits) – IP version, normally 4 for IPv4
- **IHL**	(8 bits) – header length
- **DSCP/ECN** (16 bits) – traffic classification and congestion signalling
- **total length** (32 bits) – size of the complete IP packet, including the header
- **identification** (32 bits) – helps reassemble fragmented packets
- **Flags** (8 bits) – controls fragmentation
- **fragment offset** (24 bits) – position of a fragment in the original packet
- **TTL** (8 bits) – limits how many routers a packet can traverse
- **protocol** (8 bits) – identifies the next protocol, such as TCP (6) or UDP (17)
- **header checksum** (16 bits) – checks for errors in the IPv4 header
- **source IP** (32 bits) – sender’s IP address
- **destination IP** (32 bits) – intended recipient’s IP address


## Routing

a computer decides which computer to send a packet to next, based on the ultimate destination IP address

uses a routing table 

A routing table maps sets of incoming IP addresses to the appropriate outgoing IP addresses.

Uses CIDR notation to describe a set of IP addresses (ie. a subnet)

eg. `192.168.1.0/24` means `192.168.1.*` or `192.168.1.0` to `192.168.1.255`. (subnet mask)

The 24 means the subnet is identified by the first 24 bits – the first three segments.

After forwarding the router normally decrements the packets TTL (time to live) – this stops a packet circulating forever – when TTL reaches zero, the packet is discarded.

Two approaches to routing:
- static routing – configured manually by a network admin
- dynamic routing – the routing table is continually updated based on feedback from the internet

When a router receives an IP packet, it typically:
1. Reads the destination IP address.
2. Consults its routing table to decide where to forward the packet.
3. Decreases the TTL by one.
4. Updates the IPv4 header checksum.
5. Forwards the packet towards its destination.


----

Back up to: [Maglocvnus](../index.md)
