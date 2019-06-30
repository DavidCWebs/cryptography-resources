Counter (CTR) Mode
==================
Unlike CBC mode, no data dependency. Each ciphertext block results from xoring the message block with the encrypted counter concatenated with a nonce:

```
ci = Ek(nonce || i) xor mi
```
In this mode, we can precompute all the encryptions (the expensive process) even before the message is known. We just need the nonce, the key and the counter.

This can be computed in parallel, as can the final xor with the message blocks.
