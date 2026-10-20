# Transport Layer Security

`Transport Layer Security` (TLS) is a set of rules governing how data can be transferred in a private and trustworthy manner across the internet from one computer to another.

1. Client: Here is my certificate proving who I am
2. Server: I trust the organisation that issued that certificate
3. Both: Let'd agree on secret encryption keys
4. A secure TLS connection is established
5. Client and server can now communicate securely.

## Encryption




## Authentication

TLS certificates
- Are you communicating with an imposter server?

## Integrity

Messages cannot be altered in transit


## TLS handshake

1. The client sends a `ClientHello` message to the server (over TCP over IP? just over IP?)
   - “Hello! I support TLS 1.3 and these encryption options. Here is some information we can use to agree encryption keys.”
   - The client normally includes a temporary cryptographic key share here, to speed things up.

2. The server sends a `ServerHello` message back to the client
   - “Great! Let’s use TLS 1.3, this cryptographic description, and here is my key share.”

3. The two computers independently use the two **key shares** to calculate the same **shared secret** (without sending it across the internet).

4. The server sends another message to the client, containing its **TLS certificate**, along with cryptographic proof that it posses the **private key** corresponding to this certificate.

5. The client verifies the certificate through the **certificate trust chain**.
  - “Is this certificate valid? Is it for the right server? Do I trust the certificate issuer?”

6. Both client and server then independently derive **encryption keys** from the shared secret.

7. Both sides send a cryptographically protected `Finished` message.

8. Normal communication begins.


----

Back up to: [Maglocvnus](../index.md)
