---
title: "🔢 Max Sum Increasing Subsequence | GFG Solution 🔍"
keywords🏷️: ["🔢 max sum", "📈 increasing subsequence", "🔍 dynamic programming", "📊 DP optimization", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Max Sum Increasing Subsequence problem: find maximum sum of strictly increasing subsequence using dynamic programming and optimized approaches. 🚀"
date: 📅 2025-11-17
---

# *321. Max Sum Increasing Subsequence*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/maximum-sum-increasing-subsequence4749/1)

## **🧩 Problem Description**

You are given an array `arr[]` consisting of positive integers. Your task is to find the **maximum sum** of a subsequence such that the elements of the subsequence form a **strictly increasing sequence**.

In other words, among all strictly increasing subsequences of the array, return the one with the largest possible sum.


## Code(C++)
```cpp
class Solution {
public:
    int maxSumIS(vector<int>& arr) {
        int n = arr.size();
        int res = 0;
        vector<int> dp(n);
        for (int i = 0; i < n; i++) {
            dp[i] = arr[i];
            for (int j = 0; j < i; j++) {
                if (arr[j] < arr[i])
                    dp[i] = max(dp[i], dp[j] + arr[i]);
            }
            res = max(res, dp[i]);
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public int maxSumIS(int[] arr) {
        int n = arr.length;
        int res = 0;
        int[] dp = new int[n];
        for (int i = 0; i < n; i++) {
            dp[i] = arr[i];
            for (int j = 0; j < i; j++) {
                if (arr[j] < arr[i])
                    dp[i] = Math.max(dp[i], dp[j] + arr[i]);
            }
            res = Math.max(res, dp[i]);
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def maxSumIS(self, arr):
        n = len(arr)
        dp = arr[:]  
        for i in range(n):
            for j in range(i):
                if arr[j] < arr[i]:
                    dp[i] = max(dp[i], dp[j] + arr[i])
        return max(dp)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
