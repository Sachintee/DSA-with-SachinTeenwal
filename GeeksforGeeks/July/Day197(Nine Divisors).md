---
title: "🔢 Nine Divisors | GFG Solution 🔍"
keywords🏷️: ["🔢 nine divisors", "🔍 number theory", "📍 sieve", "📈 prime factors", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Nine Divisors problem: count numbers ≤ n having exactly 9 divisors using sieve and prime factorization technique. 🚀"
date: 📅 2025-07-16
---

# *197. Nine Divisors*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/nine-divisors3751/1)

## **🧩 Problem Description**

Given a positive integer `n`, you need to count the numbers less than or equal to `n` having exactly **9 divisors**.


### 📌 Key Insight:

A number has exactly 9 divisors if and only if its prime factorization fits into one of the following patterns:

* $p^8$ → 9 divisors (as $(8 + 1) = 9$)
* $p^2 \cdot q^2$ → 9 divisors (as $(2 + 1)(2 + 1) = 9$), where $p \ne q$


## Code(C++)
```cpp
class Solution {
public:
    int countNumbers(int n) {
        int c = 0, lim = sqrt(n);
        vector<int> spf(lim + 1);
        iota(spf.begin(), spf.end(), 0);
        for (int i = 2; i * i <= lim; ++i)
            if (spf[i] == i)
                for (int j = i * i; j <= lim; j += i)
                    if (spf[j] == j) spf[j] = i;
        for (int i = 2; i <= lim; ++i) {
            int p = spf[i], q = spf[i / p];
            if (p * q == i && p != q && q != 1) ++c;
            else if (spf[i] == i && pow(i, 8) <= n) ++c;
        }
        return c;
    }
};
```

## Code (Java)

```java
class Solution {
    public static int countNumbers(int n) {
        int c = 0, lim = (int)Math.sqrt(n);
        int[] spf = new int[lim + 1];
        for (int i = 2; i <= lim; i++) spf[i] = i;
        for (int i = 2; i * i <= lim; i++)
            if (spf[i] == i)
                for (int j = i * i; j <= lim; j += i)
                    if (spf[j] == j) spf[j] = i;
        for (int i = 2; i <= lim; i++) {
            int p = spf[i], q = spf[i / p];
            if (p * q == i && p != q && q != 1) c++;
            else if (spf[i] == i && Math.pow(i, 8) <= n) c++;
        }
        return c;
    }
}
```

## Code (Python)

```python
class Solution:
    def countNumbers(self, n):
        from math import isqrt
        c, lim = 0, isqrt(n)
        spf = list(range(lim + 1))
        for i in range(2, isqrt(lim) + 1):
            if spf[i] == i:
                for j in range(i*i, lim + 1, i):
                    if spf[j] == j: spf[j] = i
        for i in range(2, lim + 1):
            p, q = spf[i], spf[i // spf[i]]
            if p * q == i and p != q and q != 1: c += 1
            elif spf[i] == i and i**8 <= n: c += 1
        return c
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
