---
title: "🧮 Get Minimum Squares | GFG Solution 🔍"
keywords🏷️: ["🧮 perfect squares", "📏 dynamic programming", "📉 BFS", "💭 Lagrange theorem", "🔢 number theory",  "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution for Get Minimum Squares problem: find the minimum number of perfect squares that sum up to n using mathematical theorem and alternative DP approaches. 🚀"
date: 📅 2025-11-05
---


# **309. Get Minimum Squares**

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/get-minimum-squares0538/1)

## **🧩 Problem Description**

Given a positive integer `n`, find the minimum number of perfect squares (square of an integer) that sum up to `n`.

**Note:** Every positive integer can be expressed as a sum of square numbers since 1 is a perfect square, and any number can be represented as 1*1 + 1*1 + 1*1 + ....


## Code(C++)
```cpp
class Solution {
public:
    int minSquares(int n) {
        if(int s = sqrt(n); s * s == n) return 1;
        for(int i = 1; i * i <= n; i++)
            if(int r = sqrt(n - i * i); r * r == n - i * i) return 2;
        while(n % 4 == 0) n /= 4;
        return n % 8 == 7 ? 4 : 3;
    }
};
```

## Code (Java)

```java
class Solution {
    public int minSquares(int n) {
        int s = (int)Math.sqrt(n);
        if(s * s == n) return 1;
        for(int i = 1; i * i <= n; i++) {
            int r = (int)Math.sqrt(n - i * i);
            if(r * r == n - i * i) return 2;
        }
        while(n % 4 == 0) n /= 4;
        return n % 8 == 7 ? 4 : 3;
    }
}
```

## Code (Python)

```python
class Solution:
    def minSquares(self, n):
        s = int(n ** 0.5)
        if s * s == n: return 1
        for i in range(1, int(n ** 0.5) + 1):
            r = int((n - i * i) ** 0.5)
            if r * r == n - i * i: return 2
        while n % 4 == 0: n //= 4
        return 4 if n % 8 == 7 else 3
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
