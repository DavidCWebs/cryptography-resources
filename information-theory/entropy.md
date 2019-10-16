Entropy
=======
[Information Entropy][4] is the average rate at which information is produced by a stochastic(random) source of data.

What is Information?
--------------------
Information is what you get when uncertainty around an event is decreased. Before a fair coin-toss, there is an equal probabilty of the toss resulting in heads or tails - the result is uncertain. After the toss, there is no more uncertainty and information (the result of the toss) has been gained.

The amount of information in a message is defined as the minimum number of bits required to represent all possible meanings of the message, assuming that all messages are equally likely ([Scshneier, 1996][5]).

In terms of the coin toss, because there are only two outcomes you can represent all possible outcomes with a single bit.

Entropy is used to quantify uncertainty. For a coin toss, entropy is 1 since this represents the minimum number of bits to represent all possible outcomes.

Definition of Entropy
---------------------
Entropy is a way of measuring the uncertainty of a stochastic variable [Schiffman][3].

The amount of information that could be conveyed by a message is measured by the **entropy** of the message.

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
| Unused      | 111 |

There are 7 potential days of the week, so the information must be represented by a minimum of 7 binary states.
How many bits are required to represent 7 distinct states?

The lowest number that can represent 7 states is 6: `{0, 1, 2, 3, 4, 5, 6}` - as shown above in binary format. The number 6 represented in binary format is 110, or 2<sup>2.59</sup>, or log<sub>2</sub> 6.

Because a binary system represents data in discrete bits, the number of bits required to represent a number must be an integer not a fraction. In this case, 3 bits are required to represent the 7 states.

In a base 2 system, this generalises to 2<sup>n</sup> where n is the minimum number of digits required to represent all possible states.

Entropy, though measured in bits, is __not__ information. It is rather a measurement of how much information is __not available__ when the outcome of a random source of information is unknown.


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
* 8 bits: 256 different values

Practical Uses
--------------
When calculating the entropy of a password or passphrase, entropy is defined as log base 2 of the number of characters/words that the password has been randomly selected from to the power of the password/passphrase length.

The Bash script below calculates the entropy of words that have been pseudo-randomly selected from a word list. In this case, character set is the number of words available to select from and the length is the number of pseudorandom words output.

```bash
#/bin/bash
...
function entropy {
	export WORDSET=$1
	export WORDS=$2
	python3 - <<- EOF
	import math; import os;
	# Entropy is log base 2 of the keyspace to the power of the length 
	r = math.log(int(os.environ['WORDSET']) ** int(os.environ['WORDS']), 2)
	print(round(r, 2))
	EOF
}
```

Resources
---------
* [Good short description of entropy][1]
* [Verbose description of entropy][2]
* [On Information entropy][3], Cisco blog
* [Information Entropy][4], Wikipedia


[1]: https://math.stackexchange.com/a/768356/559161
[2]: http://pages.cs.wisc.edu/~sriram/ShannonEntropy-Intuition.pdf
[3]: https://blogs.cisco.com/security/on_information_entropy
[4]: https://en.wikipedia.org/wiki/Entropy_(information_theory)
[5]: https://www.amazon.com/Applied-Cryptography-Protocols-Algorithms-Source/dp/1119096723/ref=sr_1_1?keywords=applied+cryptography&qid=1562511120&s=books&sr=1-1
