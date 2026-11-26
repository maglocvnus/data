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


----

Back up to: [Maglocvnus](../index.md)
