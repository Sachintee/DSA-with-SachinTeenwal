---
title: "📐 Sum of Subarrays | GFG Solution 🔍"
keywords🏷️: ["📐 sum of subarrays", "🔍 mathematical formula", "📍 contribution technique", "📈 array optimization", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Sum of Subarrays problem: calculate total sum of all possible subarrays using mathematical contribution technique. 🚀"
date: 📅 2025-07-23
---

# *204. Sum of Subarrays*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/sum-of-subarrays2229/1)

## **🧩 Problem Description**

Given an array `arr[]`, find the sum of all the subarrays of the given array.

A subarray is a contiguous sequence of elements within an array. The goal is to calculate the total sum of all possible subarrays efficiently.

**Note:** It is guaranteed that the total sum will fit within a 32-bit integer range.


## Code(C++)
```cpp
class Solution {
public:
    int subarraySum(vector<int>& arr) {
        int n = arr.size(), sum = 0;
        for (int i = 0; i < n; ++i)
            sum += arr[i] * (i + 1) * (n - i);
        return sum;
    }
};
```

## Code (Java)

```java
class Solution {
    public int subarraySum(int[] arr) {
        int n = arr.length, sum = 0;
        for (int i = 0; i < n; ++i)
            sum += arr[i] * (i + 1) * (n - i);
        return sum;
    }
}
```

## Code (Python)

```python
class Solution:
    def subarraySum(self, arr):
        n = len(arr)
        return sum(arr[i] * (i + 1) * (n - i) for i in range(n))
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
