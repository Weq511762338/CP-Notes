---
description: A page dedicated to the brilliant intersection between math and cp problems
---

# Bit-wise Operators

Bit wise operators include common ones: &, |, ^, etc. They act on bits representation of data such as integers.



## Cool Tricks and Properties

### XOR Operator

XOR operator (^) is **associative**, **commutative**, and **reversible**. Whenever you face a problem involving the XOR concept, try to use these properties. They will save you a lot of time and sometimes they are the key to the solutions.

These properties mean that the order of a series of XOR operations does not matter. Most importantly, prefix sum can be applied if needed.

{% embed url="https://leetcode.com/problems/count-triplets-that-can-form-two-arrays-of-equal-xor/description/" %}

One interesting property is that XOR operation is **reversible**. To get to the pre-XORed number, just XOR again with the same number. **XORing the same number twice cancels the effects**. This property allows problems like [Single Number](https://leetcode.com/problems/single-number/description/) to be solved like magics.
