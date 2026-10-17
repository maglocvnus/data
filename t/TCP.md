# Transmission Control Protocol

`Transmission Control Protocol` (TCP) is a set of rules for exchanging data **reliably** between two computers across a network, ensuring that the data arrives complete, in the correct order, and without errors.

TCP covers the following areas of networking:
- how to establish and close a connection between two computers (a client and a server)
- mmm

## Establishing and closing connections

TCP mandates the ‘three-way handshake’ as the means of establishing a connection between a client and a server (more specifically between the networking stacks of the operating systems running on the two computers).

This works as follows:

1. The client OS constructs a (20-byte) TCP header segment, with:
  - the `SYN` flag set to `1` (ie. to request a sequence number synchronisation)
  - the ‘sequence number’ set to some initial 32-bit integer eg. `1000`.
2. The client OS sends an IP packet containing this TCP segment to the selected server — *This is segment 1000, and I want to talk to you*.
3. The client OS changes its internal state from `closed` to `syn-sent`.
4. In response, the server OS constructs a TCP segment, with:
  - both the `ACK` and `SYN` flags set to `1` (ie. acknowledging receipt of the client’s synchronisation request, and making its own synchronisation request)
  - the sequence number set to some initial 32-bit integer eg. `5000`
  - the ‘acknowledgement number’ set to the client’s next sequence number, ie. `1001`.
4. The server OS sends an IP packet containing this TCP segment back to the client — *This is segment 5000, I am happy to talk to you, and I expect your next segment to be 1001.*
5. The server OS changes its internal state from `listen` to `syn-received`.
6. In response, the client OS constructs a TCP segment, with:
  - the `ACK` flag set to `1` (ie. acknowledging receipt of the server’s synchronisation request)
  - the sequence number set to `1001`
  - the acknowledgement number set to `5001`.
7. The client OS sends an IP packet containing this TCP segment back to the server — *This is segment 1001, and I expect your next segment to be 5001.*
8. The client OS changes its internal state from `syn-sent` to `established`.
9. In response, the server OS changes its internal state from `syn-received` to `established`.

`FIN`




## Data segmentation

packets

## Confirmation of receipt


## Retransmission of missing packets


----

Back up to: [Maglocvnus](../index.md)
