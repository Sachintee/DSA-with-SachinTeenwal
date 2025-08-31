---
title: "🌊 Container With Most Water | GFG Solution 💧"
keywords🏷️: ["🌊 container water", "🔍 two pointers", "📍 sliding window", "📈 greedy algorithm", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Container With Most Water problem: find maximum water area between two vertical lines using optimal two-pointer technique. 🚀"
date: 📅 2025-08-31
---

# *243. Container With Most Water*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/container-with-most-water0535/1)

## **🧩 Problem Description**

Given an array `arr[]` of non-negative integers, where each element `arr[i]` represents the height of vertical lines, find the **maximum amount of water** that can be contained between any two lines, together with the x-axis.

**Note:** In the case of a single vertical line, it will not be able to hold water.

The water area is calculated as: **Area = min(height[i], height[j]) × (j - i)** where i and j are indices of two lines.


## Code(C++)
```cpp
class Solution {
public:
    int maxWater(vector<int>& h) {
        int l = 0, r = h.size() - 1, ans = 0;
        while (l < r) {
            ans = max(ans, min(h[l], h[r]) * (r - l));
            h[l] < h[r] ? ++l : --r;
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int maxWater(int[] h) {
        int l = 0, r = h.length - 1, max = 0;
        while (l < r) {
            max = Math.max(max, Math.min(h[l], h[r]) * (r - l));
            if (h[l] < h[r]) l++; else r--;
        }
        return max;
    }
}
```

## Code (Python3)

```python
class Solution:
    def maxWater(self, h):
        l, r, ans = 0, len(h) - 1, 0
        while l < r:
            ans = max(ans, min(h[l], h[r]) * (r - l))
            l, r = (l + 1, r) if h[l] < h[r] else (l, r - 1)
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
