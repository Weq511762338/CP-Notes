---
description: Nightmare...
---

# Modulo

Modulo is known as a math operation: `%` . It yields the remainder after a division operation.

But, there is more than that. There is a whole field in math that deals with modulo arithmetics.



## Remainder/Divisibility

Mod is commonly used to check if a number is divisible by another number when the remainder is 0.&#x20;

When it comes to remainders, for a division like: `a/b=c...r` , `r < b` is true always. One classic principle is that, if the number being divided increases in a repeated patterns, the order of remainders occurring will follow a special pattern, too:&#x20;

1\) There will be at most `b` remainders

2\) The remainders will occur in a cyclic fashion, due to the Pigeonhole Principle.&#x20;

Especially rule 2), it can shrink down the problem size by a lot when needed to check a large quantity.

## Modulo Ouput

It is common to see some problems require an output that is claimed to be very large, and asked to output under a MOD. An example MOD would be `1e9+7`. It is not too hard to just add up numbers and take a MOD afterward. Multiplication follow similar rules. You might think this is not bad at all and just easy math, until...

Division operation under a MOD is not as simple as one would think. If two numbers are already under the MOD, simply dividing them traditionally would not yield the same result.&#x20;

Modular Inverse comes to the rescue. In essence, just like how dividing a number by `x`  is the same as multiplying by its inverse, `1/x`There is a modular inverse that one can find, so multiplication can be performed instead of division.

To find the inverse, we introduce the **Fermat's Little Theorem**, which states that: $$\frac{a}{b} \mod p = a \times b^{p-2} \mod p$$

The inverse is thus the $$b^{p-2}$$ term.&#x20;

This exponentiation can take a long time, as `p = 1e9 + 7` . But we can use fast `pow` technique to compute it.&#x20;

```cpp
long long modInverse(long long b, long long mod) {
    long long res = 1, exp = mod - 2;
    while (exp) {
        if (exp % 2)
            res = (res * b) % mod;
        b = (b * b) % mod;
        exp /= 2;
    }
    return res;
}
```

{% embed url="https://codeforces.com/contest/2043/problem/B" %}
