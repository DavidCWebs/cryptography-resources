Block Cipher Modes of Operation
===============================
A block cipher mode of operation is an algorithm that uses a block cipher to provide information security or authenticity.

A block cipher provides secure cryptographic transformation (encryption/decryption) of a fixed-length group of bits called a block.

A block cipher mode of operation describes how to apply the single block operation to a group of blocks, securely transforming data.

Modes of Operation
------------------
* Electronic Code Book (ECB)
* Cipher Block Chaining (CBC)
* Cipher Feedback Mode (CFB)
* Counter Mode (CTR)

Initialization Vector
---------------------
Most modes of encryption require a unique binary sequence called an Initialization Vector (IV). The IV must be non-repeating and for some modes it needs to be random.

The IV ensures that unique ciphertexts are produced even when the same plaintext is encrypted multiple times with the same key.

The property whereby repeated use of the scheme with the same key does not allow an attacker to feasibly/practically infer relationships between segments of the message is known as **semantic security**.

References
----------
* [Wikipedia][1]
* [Initializaton Vector][2]

[1]: https://en.wikipedia.org/wiki/Block_cipher_mode_of_operation 
[2]: https://en.wikipedia.org/wiki/Initialization_vector
