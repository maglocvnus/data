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

### 1. ClientHello

The client sends a `ClientHello` message to the server (over TCP over IP? just over IP?)

#### 1.1. Version negotiation

The client tells the server which TLS versions it understands (so the server can then choose a version both sides support)

eg.

```
supported_versions:
    TLS 1.3
    TLS 1.2
```

#### 1.2. Cipher suites

The client tells the browser which symmetric encryption options it supports (so the server can choose one it also supports).

"These are the encryption algorithms I know how to use."

eg.

```
TLS_AES_128_GCM_SHA256
TLS_AES_256_GCM_SHA384
TLS_CHACHA20_POLY1305_SHA256
```

#### 1.3. Server Name Induction 

The client tells the server which hostname it wants to reach (since one physical server or load balancer can host hundreds of websites, and ).

```
server_name: www.example.com
```

#### 1.4. Supported groups

The client tells the server which methods/groups it supports for establishing shared cryptographic secrets.

```
supported_groups:

X25519
```

“These are the mathematical systems I know how to use for agreeing a secret with you.”

#### 1.5. Key share

The client tells the server its key share immediately (rather than waiting for the server to respond).
- The public part of the key share can safely cross the internet
- The associated private value stays client-side.

#### 1.6. Signature algorithms

The client tells the server which signature algorithms it understands.

“If you are going to prove ownership of your certificate’s key, here are the kinds of signatures I know how to verify.”

TLS supports server authentication using asymmetric cryptography, using mechanisms like RSO, ECDSA, EdDSA.




A Client hello is normally sent inside a TLS record over an already established TCP connection.



### ServerHello

2. The server sends a `ServerHello` message back to the client
   - “Great! Let’s use TLS 1.3, this cryptographic description, and here is my key share.”

3. The two computers independently use the two **key shares** to calculate the same **shared secret** (without sending it across the internet).

4. The server sends another message to the client, containing its **TLS certificate**, along with cryptographic proof that it posses the **private key** corresponding to this certificate.

5. The client verifies the certificate through the **certificate trust chain**.
  - “Is this certificate valid? Is it for the right server? Do I trust the certificate issuer?”

6. Both client and server then independently derive **encryption keys** from the shared secret.

7. Both sides send a cryptographically protected `Finished` message.

8. Normal communication begins.

## Private and public keys




----

Back up to: [Maglocvnus](../index.md)
