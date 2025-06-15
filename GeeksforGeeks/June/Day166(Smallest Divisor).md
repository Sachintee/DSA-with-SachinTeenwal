---
title: "🧮 Smallest Divisor | GFG Solution 🎯"
keywords🏷️: ["🧮 smallest divisor", "🔍 binary search", "📈 array", "🎯 optimization", "📉 greedy", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Smallest Divisor problem: find the smallest divisor such that sum of ceiling divisions is ≤ k using binary search. 🚀"
date: 📅 2025-06-15
---

# *166. Smallest Divisor*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/smallest-divisor/1)

## **🧩 Problem Description**

Given an integer array `arr[]` and an integer `k` (where `k ≥ arr.length`), find the **smallest positive integer divisor** such that the sum of the ceiling values of each element in `arr[]` divided by this divisor is **less than or equal to k**.

For a divisor `d`, the sum is calculated as: `⌈arr[0]/d⌉ + ⌈arr[1]/d⌉ + ... + ⌈arr[n-1]/d⌉ ≤ k`


## Code(C++)
```cpp
class Solution {
public:
    int smallestDivisor(vector<int>& arr, int k) {
        int l = 1, h = *max_element(arr.begin(), arr.end()), n = arr.size();
        while (l < h) {
            int m = l + (h - l) / 2, s = 0;
            for (int i = 0; i < n; ++i)
                s += (arr[i] + m - 1) / m;
            if (s <= k) h = m;
            else l = m + 1;
        }
        return l;
    }
};
```

## Code (Java)

```java
class Solution {
    int smallestDivisor(int[] arr, int k) {
        int l = 1, h = Arrays.stream(arr).max().getAsInt();
        while (l < h) {
            int m = l + (h - l) / 2, s = 0;
            for (int x : arr)
                s += (x + m - 1) / m;
            if (s <= k) h = m;
            else l = m + 1;
        }
        return l;
    }
}
```

## Code (Python)

```python
class Solution:
    def smallestDivisor(self, arr, k):
        l, h = 1, max(arr)
        while l < h:
            m, s = l + (h - l) // 2, 0
            for x in arr:
                s += (x + m - 1) // m
            if s <= k:
                h = m
            else:
                l = m + 1
        return l
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
