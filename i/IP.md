# Internet Protocol

The `Internet Protocol` (IP) is a set of rules governing how data should be transferred across the internet from one computer to another.

IP is a **best effort** delivery protocol – it attempts to deliver each packet, but makes no promise of success. Reliability can be achieved by embedding a [TCP](../t/TCP.md) segment within each IP packet.

## Addresses

Every computer on the internet has a unique IP address.

An IP address consists of 32 bits, usually represented in dotted decimation notation for readability – four base-10 octets (ie. 0 to 255), separated by dots.

Examples of IP addresses are:
- `192.168.1.25`
- `8.8.8.8`

### IPv6

The original IP addresses, discussed above, are nowadays known as IPv4.

IPv6 addresses consist of 128 bits, usually represented as four hexadecimal numbers (`0` to `FFFFFFFF`) separated by colons.

For example:
- `2001:db8::1`

## Packets

A message in IP is known as a `packet`.

An IP packet consists of:
- an obligatory 20-byte header
- an optional payload.

The header contains the following parts:
- **version** (8 bits) – IP version, normally 4 for IPv4
- **IHL**	(8 bits) – header length
- **DSCP/ECN** (16 bits) – traffic classification and congestion signalling
- **total length** (32 bits) – size of the complete IP packet, including the header
- **identification** (32 bits) – helps reassemble fragmented packets
- **Flags** (8 bits) – controls fragmentation
- **fragment offset** (24 bits) – position of a fragment in the original packet
- **time to live (TTL)** (8 bits) – limits how many routers a packet can traverse
- **protocol** (8 bits) – identifies the next protocol, such as TCP (6) or UDP (17)
- **header checksum** (16 bits) – checks for errors in the IPv4 header
- **source IP** (32 bits) – sender’s IP address
- **destination IP** (32 bits) – intended recipient’s IP address

The maximum size of an IP packet is 65,535 bytes.

However, most are much smaller since the maximum size of a ethernet frame is 1500 bytes, and packets are typically embedded in ethernet frames when travelling across local networks.

## Routing

When a router receives an IP packet, it typically:
1. Reads the destination IP address.
2. Consults its routing table to decide where to forward the packet.
3. Decreases the TTL by one. (This stops a packet circulating forever – when the TTL reaches zero, the packet is discarded.)
4. Updates the IPv4 header checksum.
5. Forwards the packet towards its destination.

A routing table maps IP network prefixes to outgoing IP addresses.

Network prefixes (or ‘subnets’) are usually written using CIDR notation.

For example, the IP prefix `192.168.1.0/24` describes all the IP addresses that come under the first 24 bits of `192.168.1.0`, ie. `192.168.1.0` to `192.168.1.255`.

There are two basic approaches to routing:
- **static** routing – the touting table is configured manually by a network administrator
- **dynamic** routing – the routing table is continually updated based on feedback from the internet.

----

Back up to: [Maglocvnus](../index.md)
