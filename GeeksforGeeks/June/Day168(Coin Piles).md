---
title: "🪙 Coin Piles | GFG Solution 🎯"
keywords🏷️: ["🪙 coin piles", "🎯 sliding window", "📊 sorting", "🔄 two pointers", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Coin Piles problem: minimize coins removed to maintain difference ≤ k between any two piles using sliding window technique. 🚀"
date: 📅 2025-06-17
---

# *168. Coin Piles*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/coin-piles5152/1)

## **🧩 Problem Description**

You are given an array `arr[]` of integers, where each element represents the number of coins in a pile. You are also given an integer `k`. Your task is to remove the **minimum number of coins** such that the absolute difference between the number of coins in any two updated piles is **at most k**.

**Note:** You can also remove a pile by removing all the coins of that pile.


## Code(C++)
```cpp
class Solution {
public:
    int minimumCoins(vector<int>& a, int k) {
        sort(a.begin(), a.end());
        int n = a.size(), t = accumulate(a.begin(), a.end(), 0), res = t, w = 0, p = 0, e = 0;
        for (int s = 0; s < n; s++) {
            while (e < n && a[e] - a[s] <= k) w += a[e++];
            int r = max(0, (t - p - w) - (n - e) * (a[s] + k));
            res = min(res, p + r);
            if (e == s) e++; else w -= a[s];
            p += a[s];
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public int minimumCoins(int[] a, int k) {
        Arrays.sort(a);
        int n = a.length, t = Arrays.stream(a).sum(), res = t, w = 0, p = 0, e = 0;
        for (int s = 0; s < n; s++) {
            while (e < n && a[e] - a[s] <= k) w += a[e++];
            int r = Math.max(0, (t - p - w) - (n - e) * (a[s] + k));
            res = Math.min(res, p + r);
            if (e == s) e++; else w -= a[s];
            p += a[s];
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def minimumCoins(self, a, k):
        a.sort()
        n, t, res, w, p, e = len(a), sum(a), sum(a), 0, 0, 0
        for s in range(n):
            while e < n and a[e] - a[s] <= k:
                w += a[e]
                e += 1
            r = max(0, (t - p - w) - (n - e) * (a[s] + k))
            res = min(res, p + r)
            if e == s: e += 1
            else: w -= a[s]
            p += a[s]
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
