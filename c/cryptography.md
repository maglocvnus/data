# Cryptographic algorithms

A `cryptographic algorithm` is a precisely defined mathematical procedure that operates on binary data (ie. bit strings), in order to protect and secure it against unauthorised access, alteration or impersonation.

There are two main kinds of cryptographic algorithm:
- `keyed`
- `unkeyed`.

A **keyed** cryptographic algorithm takes two inputs – some binary data to be operated on, and a cryptographic key.

The Advanced Encryption Standard (AES) encryption and decryption algorithms are examples of keyed cryptographic algorithms. Each of these algorithms comes in three different versions, depending on the size of the cryptographic key (in bits) – AES-128, AES-192, AES-256. Larger keys require more processing for encryption and decryption, but also offer greater security.

The AES algorithms are **block-based** – they divide the binary data into 128-bit blocks and operate on each of these independently. The AES encryption and decryption algorithms make up a **symmetric** pair, in that the same key is used for both encryption and for decryption. In other words, for every bit string *b* and every key *k*: 
- decrypt(encrypt(*d*,*k*),*k*) = *d*. 

An **unkeyed** cryptographic algorithm takes just the one input – the binary data to be operated on.

The Secure Hash Algorithms (SHA) are examples of unkeyed cryptographic algorithms. Each of these algorithms takes a bit string of arbitrary length as input and outputs a hash/digest/fingerprint consisting of a fixed number of bits – SHA-1 (160 bits), SHA-224, SHA-256, SHA-384, SHA-512. Every time a hash algorithm operates on the same bit string, exactly the same output hash will be produced. However, given a hash, it is computationally infeasible to reconstruct the original input, and even a tiny change to the input will normally produced a completely different-looking hash.

Public key encryption algorithms? RSA?

RSA is a public key encryption algorithms, using two mathematically related keys (2048 or 3072 bits long, very slow compared to AES). These keys make up an asymmetric pair.

public key - used to encrypt data, can be given to anyone

private key - kept secret and used to decrypt data

1. I want you to send me data securely.
2. I send you my public key (non-securely).
3. You use it to encrypt the data.
4. You send the encrypted data to me.
5. I decrypt it using my private key.

How do you generate a public key from a private key?

1. Randomly choose two very large prime numbers p and q.
2. public key = pq plus a public exponent
3. private key calculated using p and q using modular arithmetic.
4. It is compyrarionally unfeasible to recover the private key from the public key, because of the difficulty of factoring a very large integer back into its prime factors.

Generating a 2048-bit RSA private key:

```
> openssl genpkey -algorithm RSA -pkeyopt rsa_keygen_bits:2048 -out private.pem
```

Deriving the corresponding public key:

```
> openssl pkey -in private.pem -pubout -out public.pem
```

Alternatively:

```
ssh-keygen -t rsa -b 3072
```
This creates both 




key agreement?

Use RSA to agree shared key, then use AES to encrypt/decrypt data. 

----

Back up to: [Maglocvnus](../index.md)
