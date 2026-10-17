# Transmission Control Protocol

`Transmission Control Protocol` (TCP) is a set of rules for exchanging data **reliably** between two computers across a network, ensuring that the data arrives complete, in the correct order, and without errors.

TCP covers the following networking tasks:
- how to structure a message (or TCP `segment`)
- how to establish and close a connection between two computers (a client and a server)
- how to segment files into smaller pieces
- sequencing: how to number the pieces so they can be put back together again after transmission 
- how to send pieces across a network
- acknowledgements: how to confirm which pieces have arrived
- retransmission: how to resend any missing pieces (cf. TCP timers, timeouts?)
- flow control: how to prevent a fast sender from overwhelming a slow receiver
- congestion control: how to adjust the transmission rate to avoid overloading the network

## Segments

mm

## Connections

TCP mandates the ‘three-way handshake’ as the means of establishing a connection between a client and a server (more specifically between the networking stacks of the operating systems running on the two computers).

This works as follows:

1. The client OS constructs a (20-byte, payload-free) TCP segment, with:
  - the `SYN` flag set to `1` (ie. to request a sequence number synchronisation)
  - the ‘sequence number’ set to some initial 32-bit integer eg. `1000`.
2. The client OS sends an IP packet containing this TCP segment to the selected server — *This is segment 1000, and I want to talk to you*.
3. The client OS changes its internal state from `closed` to `syn-sent`.
4. In response, the server OS constructs a (payload-free) TCP segment, with:
  - both the `ACK` and `SYN` flags set to `1` (ie. acknowledging receipt of the client’s synchronisation request, and making its own synchronisation request)
  - the sequence number set to some initial 32-bit integer eg. `5000`
  - the ‘acknowledgement number’ set to the client’s next sequence number, ie. `1001`.
4. The server OS sends an IP packet containing this TCP segment back to the client — *This is segment 5000, I am happy to talk to you, and I expect your next segment to be 1001.*
5. The server OS changes its internal state from `listen` to `syn-received`.
6. In response, the client OS constructs a (payload-free) TCP segment, with:
  - the `ACK` flag set to `1` (ie. acknowledging receipt of the server’s synchronisation request)
  - the sequence number set to `1001`
  - the acknowledgement number set to `5001`.
7. The client OS sends an IP packet containing this TCP segment back to the server — *This is segment 1001, and I expect your next segment to be 5001.*
8. The client OS changes its internal state from `syn-sent` to `established`.
9. In response, the server OS changes its internal state from `syn-received` to `established`.

TCP mandates closing an established connection by means of a TCP header segment with the `FIN` flag set to `1`.

Note that <mark>TCP segments</mark> consist of:
- an obligatory 20-byte **header**, to manage the communication
- an optional **payload**, typically much larger (eg. 1000 bytes), containing application data.

An <mark>IP packet</mark> consists of a (20-byte) IP header followed by a TCP segment.

need to include source and destination **ports** here: usual server port for TCP is 443


## Data segmentation

packets

## Confirmation of receipt


## Retransmission of missing packets


----

Back up to: [Maglocvnus](../index.md)
