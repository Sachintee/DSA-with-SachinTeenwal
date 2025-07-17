---
title: "🧮 Power of k in factorial of n | GFG Solution 🔍"
keywords🏷️: ["🧮 power of k", "🔍 prime factorization", "📍 legendre's formula", "📈 factorial", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to find the highest power of k that divides n! using prime factorization and Legendre's formula. 🚀"
date: 📅 2025-07-17
---

# *198. Power of k in factorial of n*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/power-of-k-in-n-where-k-may-be-non-prime4206/1)

## **🧩 Problem Description**

Given two positive integers `n` and `k`, determine the highest value of `x` such that `k^x` divides `n!` (n factorial) completely (i.e., `n! % (k^x) == 0`).

The task is to find the maximum power of `k` that can divide `n!` without leaving a remainder.


## Code(C++)
```cpp
class Solution {
public:
    int maxKPower(int n, int k) {
        int res = INT_MAX;
        for (int i = 2; i * i <= k; i++) {
            if (k % i == 0) {
                int cnt = 0;
                while (k % i == 0) k /= i, cnt++;
                int fact = 0;
                for (int p = i; p <= n; p *= i) fact += n / p;
                res = min(res, fact / cnt);
            }
        }
        if (k > 1) {
            int fact = 0;
            for (int p = k; p <= n; p *= k) fact += n / p;
            res = min(res, fact);
        }
        return res == INT_MAX ? 0 : res;
    }
};
```

## Code (Java)

```java
class Solution {
    public int maxKPower(int n, int k) {
        int res = Integer.MAX_VALUE;
        for (int i = 2; i * i <= k; i++) {
            if (k % i == 0) {
                int cnt = 0;
                while (k % i == 0) { k /= i; cnt++; }
                int fact = 0;
                for (int p = i; p <= n; p *= i) fact += n / p;
                res = Math.min(res, fact / cnt);
            }
        }
        if (k > 1) {
            int fact = 0;
            for (int p = k; p <= n; p *= k) fact += n / p;
            res = Math.min(res, fact);
        }
        return res == Integer.MAX_VALUE ? 0 : res;
    }
}
```

## Code (Python)

```python
class Solution:
    def maxKPower(self, n, k):
        res = float('inf')
        i = 2
        while i * i <= k:
            if k % i == 0:
                cnt = 0
                while k % i == 0:
                    k //= i
                    cnt += 1
                fact = 0
                p = i
                while p <= n:
                    fact += n // p
                    p *= i
                res = min(res, fact // cnt)
            i += 1
        if k > 1:
            fact = 0
            p = k
            while p <= n:
                fact += n // p
                p *= k
            res = min(res, fact)
        return res if res != float('inf') else 0
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
