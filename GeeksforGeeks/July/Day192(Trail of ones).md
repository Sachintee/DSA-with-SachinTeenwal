---
title: "1️⃣ Trail of Ones | GFG Solution 🔍"
keywords🏷️: ["1️⃣ binary strings", "🔍 dynamic programming", "📍 consecutive ones", "📈 bit manipulation", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Trail of Ones problem: count binary strings of length n with at least one pair of consecutive 1's using dynamic programming approach. 🚀"
date: 📅 2025-07-11
---

# *192. Trail of Ones*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/trail-of-ones3242/1)

## **🧩 Problem Description**

Given an integer `n`, the task is to count the number of binary strings of length `n` that contains **at least one pair of consecutive 1's**.

A binary string is a sequence made up of only 0's and 1's. We need to find how many such strings of length `n` have at least one occurrence of "11" as a substring.


## Code(C++)
```cpp
class Solution {
public:
    int countConsec(int n) {
        int a = 0, b = 0;
        for (int i = n; i; i--) {
            int tmp = a + b;
            b = a + (1 << (n - i));
            a = tmp;
        }
        return a;
    }
};
```

## Code (Java)

```java
class Solution {
    public int countConsec(int n) {
        int a = 0, b = 0;
        for (int i = n; i > 0; i--) {
            int tmp = a + b;
            b = a + (1 << (n - i));
            a = tmp;
        }
        return a;
    }
}
```

## Code (Python)

```python
class Solution:
    def countConsec(self, n: int) -> int:
        a = b = 0
        for i in range(n, 0, -1):
            a, b = a + b, a + (1 << (n - i))
        return a
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
