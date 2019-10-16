Cipher Block Chaining
=====================
Electronic Code Book mode involves encrypting a message in a block-by-block fashion with the same key. This leaks:

* Message length
* Which blocks in the message are equal

Cipher Block Chaining mode avoids some of these problems.

Use ciphertext from the previous block to affect the subsequent encrypted block: the ciphertext of block n-1 is xored with message n before input to the AES encryption function.

```
m = m₀, m₁, ... mₙ₋₁ blocks of size b

cᵢ = Eₖ(mᵢ xor cᵢ₋₁) 
```
For the first block, an Initialization Vector(IV) is required - it is xored with the first block. IV doesn't need to be secret, as it will be encrypted, but better not to reuse. You can't get the first block with the IV and ciphertext alone, since the ciphertext has been encrypted with a key.

If the IV is missing, the entire ciphertext can be decrypted except for the first block.

References
----------
* [CBC Mode, Crypto++ Wiki][1]

[1]: https://cryptopp.com/wiki/CBC_Mode
