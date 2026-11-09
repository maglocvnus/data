# Transmission Control Protocol

The `Transmission Control Protocol` (TCP) is a set of rules governing how data can be transferred **reliably** across the internet from one computer to another, ensuring that the data arrives complete, in the correct order, and without errors.

TCP works on top of the [Internet Protocol](../i/IP.md) (IP). Before a TCP segment can be sent across the internet, it needs to be embedded in an IP packet as the data payload. The segment can then be unpacked and reassembled with its siblings after it has reached its destination.

Contents:
- [TCP segments](#tcp-segments)
- [the TCP handshake](#the-tcp-handshake)

## TCP segments

A segment is the basic unit of communication in TCP.

Each TCP segment consists of:
- an obligatory 20-byte **header**, containing source and destination ports, sequence number, etc.
- an optional **payload**, consisting of (potentially encrypted) application data.

maximum size? payload usually has a max of 1460 bytes coz of Ethernet frames

A TCP header contains the following parts:

|name|bytes|description|
|-|-|-|
|**source port**|2|a 16-bit unsigned integer representing an application endpoint|
|**destination port**|2|ditto|
|**sequence number**|4|the byte position where the payload begins|
|**acknowledgement number**|4|the expected next sequence number|
|**data offset**|0.7|the length of the TCP header in units of 4 bytes|
|**flags**|1.1|see below|
|**window size**|2|how many additional bytes the receiver is currently prepared to accept|
|**checksum**|2|checks for errors in the header|
|**urgent pointer**|2|only meaningful when the URG flag is set; rarely used|

The nine flag bits are as follows:
- `SYN`
- `ACK`
- `FIN`
- RST
- PSH
- URG
- ECE
- CWR
- NS


## The TCP handshake

Before a (client) computer can start exchanging data with a (server) computer, it needs to successfully establish a connection. This is done using a **three-way handshake**:
1. `SYN`: The client sends an introductory segment to the server, containing its initial sequence number — «Hello! Can we talk?»
2. `ACK-SYN`: The server responds with a segment containing its own initial sequence number — «Yes, I can hear you. Can you hear me?»
3. `ACK`: The client responds in the affirmative — «Yes, I can hear you too.»

Once the handshake is complete, the client can start sending application data to the server.

### SYN

At the start, the client’s internal TCP state is `closed`, and the server’s is `listen`.

Firstly, the client constructs a (20-byte, payload-free) TCP segment, with:
- the `SYN` flag set to `1`, to request a sequence number synchronisation
- other flags, in particular `ACK`, set to `0`
- the ‘sequence number’ set to some initial 32-bit integer, eg. `1000`
- the source and destination ports identified.

Secondly, the client packages this TCP segment as the payload of a new IP packet, whose header specifies the IP addresses of both client and server.

Thirdly, the client transmits this IP packet across the internet, in the general direction of the server.

Fourthly, the client changes its internal TCP state from `closed` to `syn-sent` — it has carried out the first step in the three-way handshake, and is awaiting a response from the server.

### ACK-SYN

Whenever an IP packet arrives at its destination, the server leaps into action.

Firstly, the server takes a note of the client’s IP address in the IP header, and extracts the TCP segment from the packet’s payload. 

Secondly, the server takes a note of the source and destination port numbers in the TCP header, identifies the segment as a SYN request, and takes a note of the client’s initial sequence number.

Thirdly, the server constructs a (20-byte, payload-free) TCP segment, with:
  - the `ACK` flag set to `1`, acknowledging receipt of the client’s synchronisation request
  - the `SYN` flag set to `1`, initiating that the server is making its own synchronisation request
  - the `sequence number` set to some initial 32-bit integer, eg. `5000`
  - the ‘acknowledgement number’ set to the client’s next sequence number, ie. `1001`
  - the source and destination ports switched around.

Fourthly, the server packages this TCP segment up as the payload of a new IP packet, with the IP addresses switched around in the header.

Fifthly, the server transmits this IP packet across the internet, in the general direction of the client. 

Sixthly, the server changes its internal TCP state from `listen` to `syn-received` — it has carried out the second step in the three-way handshake, and is now awaiting a response from the client. 

### ACK

6. In response, the client OS constructs a (payload-free) TCP segment, with:
  - the `ACK` flag set to `1` (ie. acknowledging receipt of the server’s synchronisation request)
  - the sequence number set to `1001`
  - the acknowledgement number set to `5001`.
7. The client OS sends an IP packet containing this TCP segment back to the server — *This is segment 1001, and I expect your next segment to be 5001.*
8. The client OS changes its internal state from `syn-sent` to `established`.
9. In response, the server OS changes its internal state from `syn-received` to `established`.




TCP mandates closing an established connection by means of a TCP header segment with the `FIN` flag set to `1`.



need to include source and destination **ports** here: usual server port for TCP is 443


## Data segmentation

packets

## Confirmation of receipt


## Retransmission of missing packets


- how to structure a message (or TCP `segment`)
- how to establish and close a connection between two computers (a client and a server)
- how to segment files into smaller pieces
- sequencing: how to number the pieces so they can be put back together again after transmission 
- how to send pieces across a network
- acknowledgements: how to confirm which pieces have arrived
- retransmission: how to resend any missing pieces (cf. TCP timers, timeouts?)
- flow control: how to prevent a fast sender from overwhelming a slow receiver
- congestion control: how to adjust the transmission rate to avoid overloading the network

----

Back up to: [Maglocvnus](../index.md)
