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
|**DSCP/ECN**|2|traffic handling and congestion notification|
|**total length**|2|number of bytes in the whole packet, including both header and payload|
|**identification**|2|identifies fragments of the same original packet|
|**flags**|0.3|3 bits, controls fragmentation|
|**fragment offset**|1.5|13 bits, fragment offset, position of a fragment in the original packet|
|**time-to-live (TTL)**|1|limits how far a packet can travel; every traversed router decrements TTL by (at least) one|
|**protocol**|1|identifies the next protocol, ie. what kind of data does the payload contain; eg. TCP `6`, UDP `17`|
|**header checksum**|2|checks for errors in the IPv4 header|
|**source IP**|4|sender’s IP address|
|**destination IP**|4|intended recipient’s IP address|



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
