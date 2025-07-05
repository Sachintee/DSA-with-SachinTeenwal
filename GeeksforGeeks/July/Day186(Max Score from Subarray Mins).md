---
title: "💯 Max Score from Subarray Mins | GFG Solution 🔍"
keywords🏷️: ["💯 max score", "🔍 subarray", "📍 two smallest", "📈 optimization", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Max Score from Subarray Mins problem: find maximum sum of smallest and second smallest elements across all subarrays using optimized approach. 🚀"
date: 📅 2025-07-05
---

# *186. Max Score from Subarray Mins*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/max-sum-in-sub-arrays0824/1)

## **🧩 Problem Description**

You are given an array `arr[]` of integers. Your task is to find the **maximum sum** of the **smallest and second smallest elements** across all subarrays (of size >= 2) of the given array.

A subarray is a contiguous sequence of elements within an array. For each subarray of size at least 2, we need to find the two smallest elements and calculate their sum. The goal is to find the maximum such sum across all possible subarrays.


## Code(C++)
```cpp
class Solution {
public:
    int maxSum(vector<int> &arr) {
        int ans = 0;
        for (int i = 1; i < arr.size(); i++)
            ans = max(arr[i] + arr[i - 1], ans);
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int maxSum(int arr[]) {
        int ans = 0;
        for (int i = 1; i < arr.length; i++)
            ans = Math.max(arr[i] + arr[i - 1], ans);
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def maxSum(self, arr):
        ans = 0
        for i in range(1, len(arr)):
            ans = max(arr[i] + arr[i - 1], ans)
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
