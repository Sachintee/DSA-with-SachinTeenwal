---
title: "🔢 Maximize Number of 1's | GFG Solution 🔍"
keywords🏷️: ["🔢 binary array", "🔍 sliding window", "📍 two pointers", "📈 flip zeros", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Maximize Number of 1's problem: find maximum consecutive 1's by flipping at most k zeros using optimized sliding window technique. 🚀"
date: 📅 2025-08-28
---

# *240. Maximize Number of 1's*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/maximize-number-of-1s0905/1)

## **🧩 Problem Description**

You are given a **binary array** `arr[]` containing only 0s and 1s and an integer `k`. You are allowed to **flip at most k 0s to 1s**. Your task is to find the **maximum number of consecutive 1's** that can be obtained in the array after performing the operation at most k times.

A flip operation changes a 0 to 1. The goal is to maximize the length of the longest contiguous subarray of 1's after optimally choosing which zeros to flip.


## Code(C++)
```cpp
class Solution {
public:
    int maxOnes(vector<int>& arr, int k) {
        int l = 0, zeros = 0, maxLen = 0;
        for (int r = 0; r < arr.size(); r++) {
            zeros += (arr[r] == 0);
            while (zeros > k) zeros -= (arr[l++] == 0);
            maxLen = max(maxLen, r - l + 1);
        }
        return maxLen;
    }
};
```

## Code (Java)

```java
class Solution {
    public int maxOnes(int arr[], int k) {
        int l = 0, zeros = 0, maxLen = 0;
        for (int r = 0; r < arr.length; r++) {
            if (arr[r] == 0) zeros++;
            while (zeros > k) if (arr[l++] == 0) zeros--;
            maxLen = Math.max(maxLen, r - l + 1);
        }
        return maxLen;
    }
}
```

## Code (Python3)

```python
class Solution:
    def maxOnes(self, arr, k):
        l = zeros = maxLen = 0
        for r in range(len(arr)):
            zeros += (arr[r] == 0)
            while zeros > k:
                zeros -= (arr[l] == 0)
                l += 1
            maxLen = max(maxLen, r - l + 1)
        return maxLen
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
