---
title: "📐 LCM Triplet | GFG Solution ⚙️"
keywords🏷️: ["📐 LCM triplet", "🧮 mathematical optimization", "📊 number theory", "🎯 greedy approach", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the LCM Triplet problem: find maximum possible LCM by selecting three numbers ≤ n using mathematical optimization and greedy approach. 🚀"
date: 📅 2025-07-18
---

# *199. LCM Triplet*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/lcm-triplet1501/1)

## **🧩 Problem Description**

Given a number `n`, find the **maximum possible LCM** that can be obtained by selecting three numbers less than or equal to `n`.

**Note:** LCM stands for Lowest Common Multiple.

The goal is to find three numbers ≤ n such that their LCM is maximized.

## Code(C++)
```cpp
class Solution {
public:
    int lcmTriplets(int n) {
        return n < 3 ? n : n & 1 ? n * (n - 1) * (n - 2) : 
               n % 3 ? n * (n - 1) * (n - 3) : (n - 1) * (n - 2) * (n - 3);
    }
};
```

## Code (Java)

```java
class Solution {
    int lcmTriplets(int n) {
        return n < 3 ? n : (n & 1) == 1 ? n * (n - 1) * (n - 2) : 
               n % 3 != 0 ? n * (n - 1) * (n - 3) : (n - 1) * (n - 2) * (n - 3);
    }
}
```

## Code (Python)

```python
class Solution:
    def lcmTriplets(self, n):
        return n if n < 3 else n * (n - 1) * (n - 2) if n & 1 else \
               n * (n - 1) * (n - 3) if n % 3 else (n - 1) * (n - 2) * (n - 3)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
