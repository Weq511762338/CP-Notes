# Sliding Window

A way to efficiently traverse over an array in one pass while maintaining certain properties inside the range/window. (E.g. sum)

## Counting Certain Subarrays

Typically involving the sum or product of the subarrays satisfying certain conditions, and we need to count the number of such subarrays. Using two pointers, we can construct a sliding window algorithm to efficiently count every condition-satisfying arrays in one pass.&#x20;

**Note: As we are using two pointers, this method inherently requires the monotonous properties of the numbers in the arrays. Common observations are: adding an element definitely increases the sum/product, removing an element decreases the sum/product.**

We can efficiently count the subarrays by fixing one end of the window (this pointer will be run as for-loop), and compute the other smaller subarrays once we find the smallest/largest window that satisfies the conditions.

(Sometimes it may be unnecessary/impossible to maintain both `l` and `r` pointers. But it is still a valid approach to consider all subarrays by fixing one end, either `l` or `r`, using a for-loop.)

## Exactly K

If we can solve the problem: How many **AtMost K** easily, we can find out How many **Exactly K** by `AtMost(K) - AtMost(K-1)`&#x20;

## Problems

{% embed url="https://leetcode.com/problems/binary-subarrays-with-sum/description/]" %}

{% embed url="https://leetcode.com/problems/subarray-product-less-than-k/description/" %}

{% embed url="https://leetcode.com/problems/length-of-longest-subarray-with-at-most-k-frequency/description/" %}

{% embed url="https://leetcode.com/problems/count-subarrays-with-fixed-bounds/description/" %}
