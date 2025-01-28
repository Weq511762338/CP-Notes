---
description: a.k.a "tortoise and the hare algorithm"
---

# Floyd's Cycle Detection

## Concepts

Use a `slow` pointer and `fast` pointer to traverse over a graph/linkedlist, where `slow` moves by 1 whereas `fast` moves by 2 every round. Eventually, if there is a cycle in the graph/linkedlist, `fast` and `slow` will meet at some point, indicating that a cycle exists.

Think of them as two runners on a track: Since the fast runner runs exactly **twice** as fast as the slow runner, if there exists a cycle, the two runners will inevitably meet at some moment within the cycle.

<figure><img src="../../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption></figcaption></figure>



Floyd's Cycle Detection can find more information about the cyclic graph:

## Find Cycle Length

To find the cycle length, first find the meeting point where  `fast` and `slow` pointer collides. Then the cycle length can be found by running the `slow`pointer from that meeting point until it reaches back to itself.

## Find Cycle Starting Point

After the first collision/meet point of Floyd's Cycle Detection, we set one of the pointers back to the head of the whole list. Then, running both pointers at the same speed will cause them to meet again. That meeting point is exactly the entry point of the cycle. This image illustrates it well:

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption><p>From the Medium article introduced on top of this page</p></figcaption></figure>



## Problem:

{% embed url="https://leetcode.com/problems/linked-list-cycle/description/" %}
