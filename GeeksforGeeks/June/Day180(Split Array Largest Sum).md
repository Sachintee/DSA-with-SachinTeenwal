---
title: "📏 Split Array Largest Sum | GFG Solution 🔍"
keywords🏷️: ["📏 split array", "🔍 binary search", "📈 greedy algorithm", "📊 divide conquer", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Split Array Largest Sum problem: divide array into k subarrays minimizing maximum sum using binary search and greedy approach. 🚀"
date: 📅 2025-06-29
---

# *180. Split Array Largest Sum*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/split-array-largest-sum--141634/1)

## **🧩 Problem Description**

Given an array `arr[]` and an integer `k`, divide the array into **k contiguous subarrays** such that the **maximum sum among these subarrays is minimized**. Find this minimum possible maximum sum.

The goal is to split the array optimally to minimize the largest subarray sum across all possible k-way splits.


## Code(C++)
```cpp
class Solution {
public:
    int splitArray(vector<int>& a, int k) {
        int l = *max_element(a.begin(), a.end()), r = accumulate(a.begin(), a.end(), 0);
        while (l < r) {
            int m = (l + r) / 2, s = 0, c = 1;
            for (int x : a) {
                if (s + x > m) c++, s = 0;
                s += x;
            }
            if (c <= k) r = m;
            else l = m + 1;
        }
        return l;
    }
};
```

## Code (Java)

```java
class Solution {
    public int splitArray(int[] a, int k) {
        int l = 0, r = 0;
        for (int x : a) {
            l = Math.max(l, x);
            r += x;
        }
        while (l < r) {
            int m = (l + r) / 2, s = 0, c = 1;
            for (int x : a) {
                if (s + x > m) {
                    c++;
                    s = 0;
                }
                s += x;
            }
            if (c <= k) r = m;
            else l = m + 1;
        }
        return l;
    }
}
```

## Code (Python)

```python
class Solution:
    def splitArray(self, a, k):
        l, r = max(a), sum(a)
        while l < r:
            m, s, c = (l + r) // 2, 0, 1
            for x in a:
                if s + x > m:
                    c += 1
                    s = 0
                s += x
            if c <= k: r = m
            else: l = m + 1
        return l
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
