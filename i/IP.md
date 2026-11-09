# Internet Protocol

The `Internet Protocol` (IP) is a set of rules governing how data should be transferred across the internet from one computer to another.

IP is a **best effort** delivery protocol – it attempts to deliver each packet of data, but makes no promise of success. Reliability can be achieved by embedding a [TCP](../t/TCP.md) segment within each IP packet.

## IP addresses

Every computer on the internet has a unique IP address.

An IP address consists of 32 bits, usually represented in dotted decimal notation for readability – four base-10 octets (ie. 0 to 255), separated by dots.

Examples of IP addresses are:
- `192.168.1.25`
- `8.8.8.8`

There are 2<sup>32</sup> IP addresses, just under 4.3 billion. Not all of these are available for public Internet use, however, with some being reserved for special purposes. For example, addresses starting with `192.168.*.*` are reserved for private networks. 

These original IP addresses are nowadays known as **IPv4** addresses.

**IPv6** addresses consist of 128 bits, usually represented as four hexadecimal numbers (`0` to `FFFFFFFF`) separated by colons.

Here is an example of an IPv6 address:
- `2001:db8:85a3:0000:0000:8a2e:0370:7334`

There are 2<sup>128</sup> IPv6 addresses, which is around 340 x 10<sup>36</sup>.

## IP packets

An IP packet is the basic unit of data transmitted across the internet.

Each IP packet consists of:
- an obligatory 20-byte **header**, containing the source and destination IP addresses, along with other metadata
- an optional **payload** of data, consisting of a TCP segment, a UDP datagram, etc.

Note that the header can be optionally extended to 60 bytes, if needed.

The theoretical maximum size of an IP packet, including both header and payload is 65,535 bytes. However, in practice the maximum size is 1500 bytes, since this is the maximum size of a ethernet frame (and packets are typically embedded in ethernet frames when travelling across local networks).

An IP header contains the following parts:

|name|bytes|description|
|-|-|-|
|**version**|0.4|4 bits representing the IP version assumed, normally `0100` for IPv4 or `0110` for IPv6|
|**internet header length (IHL)**|0.4|4 bits representing the total length of the header, ie. how many 4-byte units (usually `0101`)|
|**differentiated services code point (DSCP)**|0.6|6 bits indicating preferred traffic treatment, eg. priority handling for time-sensitive communications|
|**explicit congestion notification (ECN)**|0.2|2 bits indicating if compatible network devices can signal congestion without necessarily dropping packets|
|**total length**|2|number of bytes in the whole packet, including both header and payload|
|**identification**|2|associates IP fragments belonging to the same original packet|
|**flags**|0.3|3 bits specifying flags like Don’t Fragment (DF), More Fragments (MF)|
|**fragment offset**|1.5|13 bits, specifying where the IP fragment belongs in the original payload, measured in units of 8 bytes|
|**time-to-live (TTL)**|1|limits how far a packet can travel; every traversed router decrements TTL by (at least) one|
|**protocol**|1|identifies the next protocol, ie. what kind of data does the payload contain; eg. TCP `6`, UDP `17`|
|**header checksum**|2|checks for errors in the header; must be updated whenever TTL is decremented|
|**source IP**|4|sender’s IP address|
|**destination IP**|4|intended recipient’s IP address|

The three fragmentation fields are used in cases where a packet needs to be broken up, for example to traverse an Ethernet network. The original packet can then be reassembled at its destination.

**IPv6** headers are different in some important ways:
- The header is longer (40 bytes) but simpler.
- There is no header checksum.
- Source and destination IP addresses are 16 bytes longer rather than just 4.
- Routers cannot fragment packets. 

## IP routing

When an internet router receives an IP packet, it will:
1. Check that the header is valid.
2. Read the destination IP address.
3. Consult its routing table to decide which known computer/router to forward the packet to next. 
4. Decrement the TTL by one.
5. Update the header checksum.
6. Forward the packet onwards.

A **routing table** maps IP network prefixes to the IP addresses of other computers the router is connected to. 

Network prefixes (or ‘subnets’) are usually written using **CIDR** notation, for example:
- `192.168.1.0/24` includes `192.168.1.0` to `192.168.1.255`
- `192.168.0.0/16` includes `192.168.0.0` to `192.168.255.255`
- `0.0.0.0/0` includes all IPv4 addresses — the default option.

There are two basic approaches to routing:
- **static routing** – the routing table is configured manually by a network administrator
- **dynamic routing** – the routing table is continually updated based on feedback from the internet.

Note that the same IP packet may arrive twice or more at its intended destination. This **packet duplication** can be caused by network faults or by routing behaviour (eg. deliberate replication).

## Some history

1969: The first four nodes of ARPANET used packet switching (rather than the traditional circuit switching) to exchange data, using Network Control Protocol (NCP).

1974: Robert Kahn and Vint Cerf proposed a new, common protocol for ‘internetworking’, that would work across different types of network. This protocol appeared as RFC 675, and included both IP packet switching and TCP reliability mechanisms.

1978: Vint Cerf, Jon Postel and Danny Cohen proposed splitting up TCP and IP into separate protocols, essentially making the reliability mechanisms optional. This was a hugely significant moment in internet history. 

1981: Jon Postel published RFC 791, codifying IPv4.

1983: ARPANET officially transitioned from NCP to TCP/IP — the symbolic birth of the modern internet.

1993: Classless Inter-domain Routing (CIDR) introduced to make IP more scalable — allowing more efficient address allocation and routing tables. 

1994: Network Address Translation (NAT) codified in RFC 1631 — a local network can reuse private IPv4 addresses, while sharing a small number of public addresses.

2017: Standardisation of IPv6.

----

Back up to: [Maglocvnus](../index.md)
