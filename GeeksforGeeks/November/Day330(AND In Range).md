---
title: "🔢 AND In Range | GFG Solution 🔍"
keywords🏷️: ["🔢 bitwise AND", "🔍 bit manipulation", "📍 range query", "📈 Brian Kernighan", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the AND In Range problem: find bitwise AND of all numbers in range [l, r] using efficient bit manipulation techniques. 🚀"
date: 📅 2025-11-26
---

# *330. AND In Range*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/and-operation5726/1)

## **🧩 Problem Description**

You are given two integers `l` and `r`. Find the result after applying the series of **Bitwise AND ( & )** operation on every natural number between the range `l` to `r` (including both).

The bitwise AND operation compares each bit of two numbers and returns 1 only if both bits are 1. When we perform AND on a series of consecutive numbers, the result preserves only the common high-order bits (the common binary prefix) while all differing lower-order bits become 0.


## Code(C++)
```cpp
class Solution {
public:
    int andInRange(int l, int r) {
        while (l < r) r &= r - 1;
        return r;
    }
};
```

## Code (Java)

```java

```

## Code (Python)

```python

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
