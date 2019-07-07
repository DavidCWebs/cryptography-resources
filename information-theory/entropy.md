Entropy
=======
The amount of information in a message is measured by the **entropy** of the message.

The amount of information in a message is the minimum number of bits required to represent the message.

The entropy of a message indicating whether to proceed or not can be represented by a single bit, since by definition a bit has one of two states:

| Proceed? | Minimum Representation in bits |
| - | - |
| No  | 0 |
| Yes | 1 |


The days of the week can be represented by slightly less than 3 bits:

| Day of week | Minimum representation in bits |
| - | - |
| Sunday      | 000 |
| Monday      | 001 |
| Tuesday     | 010 |
| Wednesday   | 011 |
| Thursday    | 100 |
| Friday      | 101 |
| Saturday    | 110 |

There are 7 potential days of the week, so the information must be represented by a minimum of 7 binary states.
How many bits are required to represent 7 distinct states?

The lowest number that can represent 7 states is 6: `{0, 1, 2, 3, 4, 5, 6}` - as shown above in binary format. The number 6 represented in binary format is 110, or 2<sup>2.59</sup>, or log<sub>2</sub> 6.

Because a binary system represents data in discrete bits, the number of bits required to represent a number must be an integer not a fraction. In this case, 3 bits are required to represent the 7 states.

In a base 2 system, this generalises to 2<sup>n</sup> where n is the minimum number of digits required to represent all possible states.

Mnimum Representation in Bits
-----------------------------
The minimum power of 2 that is greater than or equal to the number of states.

Where the number of states is n,
```
log<sub>2</sub> n
```

The binary logarithm (log<sub>2</sub> n) is the power to which the number 2 must be raised to obtain the value n. For any real number x:

x = log<sub>2</sub>⁡ n ⟺ 2<sup>x</sup> = n.

Double a number adds 1 to binary logarithm:

| 2<sup>3</sup> (8) | 2<sup>2</sup> (4) | 2<sup>1</sup> (2) | 2<sup>0</sup> (1) | Decimal | log<sub>2</sub>⁡ n |
| - | - | - | - | - | - |
|         |       1 |       0 |       0 |       4 |           2 |
|       1 |       0 |       0 |       0 |       8 |           3 |

Upper Limits
------------
For storage of raw data, not the information content of the data:
* 2 bits: 4 different values
* 3 bits: 8 different values
* 4 bits: 16 different values
* 8 bits: 32 different values


Resources
---------
* [Good short description of entropy][1]
* [Verbose description of entropy][2]
* [On Information entropy][3]


[1]: https://math.stackexchange.com/a/768356/559161
[2]: http://pages.cs.wisc.edu/~sriram/ShannonEntropy-Intuition.pdf
[3]: https://blogs.cisco.com/security/on_information_entropy
