# Transmission Control Protocol

`Transmission Control Protocol` (TCP) is a set of rules for exchanging data reliably between two computers across a network, ensuring that the data arrives complete, in the correct order, and without errors.

## Establishing a connection between a client and a server

The two computers agree to communicate using the 3-way handshake process

1. The client constructs a (20-byte) TCP header segment, with:
  - the `SYN` flag set to `1`, requesting a sequence number synchronisation
  - the sequence number set to some initial 32-bit integer eg. `1000`.
2. The client sends an IP packet containing this TCP segment to the selected server:
  - ‘I want to talk to you, starting at 1000.’
3. The server constructs a TCP segment, with:
  - both the `ACK` and `SYN` flags set to `1`, acknowledging receipt of the client’s sequence number, and making its own synchronisation request
  - the sequence number set to some initial 32-bit integer eg. `5000`
  - the acknowledgement number set to the client’s next sequence number, ie. `1001`.
4. The server sends an IP packet containing this TCP segment back to the client:
  - ‘I am happy to talk to you. I expect your next segment to be 1001. This is segment 5000.’
5. The client constructs a TCP segment, with:
  - the `ACK` flag set to `1`, acknowledging receipt of the server’s sequence number
  - the sequence number set to `1001`
  - the acknowledgement number set to `5001`.
6. The client sends an IP packet containing this TCP segment back to the server:
  - ‘mmm’ 

## Closing a connection

`FIN`




## Data segmentation

packets

## Confirmation of receipt


## Retransmission of missing packets


----

Back up to: [Maglocvnus](../index.md)
