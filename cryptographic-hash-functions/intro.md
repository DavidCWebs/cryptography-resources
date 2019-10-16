Cryptographic Hash Functions
============================

Regular hash functions - may be used for hash table data structures.

They involve compression.

A large input domain (infinite) is compressed to a small fixed output [0, N).

Note: [0, N) the last number is excluded.

They are well distributed:

P(H(x) = i) ~ 1/n

Cryptographic Hash Functions
----------------------------
Require three additional properties:

### Pre-image Resistance
It should be hard to find the input that produced the hash.

__one-way ness__

### Weak Collision Resistance
Also called second pre-image resistance.

It is practically impossible (computationally infeasible?) to find __any input__ that hashes to the same result.

If a hash function has weak collision resistance, pre-image resistance is implied.

### Strong Collision Resistance
Hard to find any pair, x and y, such that H(x) is equal to H(y).

### Second Preimage Resistance, Weak-Collision
Computationally infeasible to find any input which hashes to that output.

[1]: https://stackoverflow.com/a/52957495/3590673
[2]: https://en.wikipedia.org/wiki/Collision_resistance
