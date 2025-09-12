---
title: "🔢 Minimize the Heights II | GFG Solution 🔍"
keywords🏷️: ["🔢 minimize heights", "🔍 greedy algorithm", "📍 sorting", "📈 optimization", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Minimize the Heights II problem: find minimum difference between tallest and shortest towers after mandatory height modifications using greedy approach. 🚀"
date: 📅 2025-09-12
---

# *255. Minimize the Heights II*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/minimize-the-heights3351/1)

## **🧩 Problem Description**

Given an array `arr[]` denoting heights of `n` towers and a positive integer `k`, you must perform exactly one of the following operations on each tower:

1. **Increase** the height of the tower by `k`
2. **Decrease** the height of the tower by `k`

Your task is to find the **minimum possible difference** between the height of the shortest and tallest towers after modification.

**Important:** After operations, the resultant array should not contain any negative integers.


## Code(C++)
```cpp
class Solution {
public:
    int getMinDiff(vector<int>& a, int k) {
        int n = a.size();
        sort(a.begin(), a.end());
        int ans = a[n-1] - a[0];
        for (int i = 1; i < n; i++) {
            if (a[i] >= k) {
                int mn = min(a[0] + k, a[i] - k);
                int mx = max(a[n-1] - k, a[i-1] + k);
                ans = min(ans, mx - mn);
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int getMinDiff(int[] a, int k) {
        Arrays.sort(a);
        int n = a.length, ans = a[n-1] - a[0];
        for (int i = 1; i < n; i++) {
            if (a[i] >= k) {
                int mn = Math.min(a[0] + k, a[i] - k);
                int mx = Math.max(a[n-1] - k, a[i-1] + k);
                ans = Math.min(ans, mx - mn);
            }
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def getMinDiff(self, a, k):
        a.sort()
        n = len(a)
        ans = a[n-1] - a[0]
        for i in range(1, n):
            if a[i] >= k:
                mn = min(a[0] + k, a[i] - k)
                mx = max(a[n-1] - k, a[i-1] + k)
                ans = min(ans, mx - mn)
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
