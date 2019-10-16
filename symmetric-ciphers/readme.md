Symmetric Ciphers
=================
Message is encrypted and decrypted with the same key.

The key is:

* Selected randomly and uniformly - no predictability about what the key is.
* Kept secret, but shared securely between participants/end-points.

The decryption with the same key of a message encrypted with that key returns the original message:

```
Dₖ(Eₖ(m)) → m
```
[AES][1] is a cipher specification that can be used for such encryption/decryption.

Key
---
All assumptions about security of encryption depend upon the key.

Key must be selected randomly.

Kolmogorov Complexity
---------------------
Measure complexity of a sequence s:

K(s) = length of the shortest possible description of s.

Description could be a Turing machine, computer programme etc.

Kolmogorov complexity is uncomputable.

Randomness
----------
A sequence is random if the shortest way to describe that sequence is equal to the length of the sequence plus a constant:

```
s is random if K(s) = |s| + C
```
As the sequence gets longer, the description gets proportionally longer.

If a short programme can produce the sequence, it is not random.

If there is no simpler way to understand the sequence than to see the whole sequence, it indicates that the sequence is random.

Unpredictability
----------------
Statistical tests can only show __non-randomness__. Cannot prove a sequence is random, since you can always find some non-random sequence that satisfies all statistical tests.

Best argument for randomness is how the sequence is generated.

s = x₀, x₁, x₂, ...x<sub>i</sub> ∈[0, 2<sup>n-1</sup>]

Each x<sub>i</sub> in the sequence is in the range from zero to 2<sup>n-1</sup>.

Even after seeing x₀..., xₘ₋₁, we can only guess xₘ with probability 1/2<sup>n</sup>.

Use a methods that generates values that are unpredictable to an attacker.

Sources of Randomness
---------------------
Physical sources:

* Quantum mechanics (e.g. measure background radioactive decay using Geiger counter)
* Thermal noise (easier to measure - if measured precisely, dependent upon quantum mechanics)

Key presses, user actions - can these be random? Unless randomness is generated from quantum physics, it is not truly random.

### Standard Approach - PRNG
Take a small amount of physical randomness and use this as a seed. This feeds a Pseudo Random Number Generator (PRNG) which generates a long sequence of "random" bits.



References
----------




[1]: https://en.wikipedia.org/wiki/Advanced_Encryption_Standard
