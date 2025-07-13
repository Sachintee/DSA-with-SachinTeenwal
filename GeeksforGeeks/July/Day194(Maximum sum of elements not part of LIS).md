---
title: "📉 Maximum Sum of Elements Not Part of LIS | GFG Solution 🔍"
keywords🏷️: ["📉 longest increasing subsequence", "🔍 binary search", "📍 dynamic programming", "📈 LIS", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Maximum Sum of Elements Not Part of LIS problem: find maximum sum of elements not in the Longest Increasing Subsequence using binary search optimization. 🚀"
date: 📅 2025-07-13
---

# *194. Maximum Sum of Elements Not Part of LIS*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/maximum-sum-of-elements-not-part-of-lis/1)

## **🧩 Problem Description**

Given an array `arr[]` of positive integers, your task is to find the maximum possible sum of all elements that are **not part of the Longest Increasing Subsequence (LIS)**.

The approach is to find the LIS with minimum sum among all possible LIS of maximum length, then subtract this from the total sum of the array.


## Code(C++)
```cpp
class Solution {
public:
    int nonLisMaxSum(vector<int>& arr) {
        vector<int> dp, sums;
        int total = accumulate(arr.begin(), arr.end(), 0);
        for (int x : arr) {
            auto it = lower_bound(dp.begin(), dp.end(), x);
            int idx = it - dp.begin();
            if (it == dp.end()) {
                dp.push_back(x);
                sums.push_back((sums.empty() ? 0 : sums.back()) + x);
            } else {
                *it = x;
                sums[idx] = (idx ? sums[idx - 1] : 0) + x;
            }
        }
        return total - sums.back();
    }
};
```

## Code (Java)

```java
class Solution {
    public int nonLisMaxSum(int[] arr) {
        ArrayList<Integer> dp = new ArrayList<>();
        ArrayList<Integer> sums = new ArrayList<>();
        int total = Arrays.stream(arr).sum();
        for (int x : arr) {
            int idx = Collections.binarySearch(dp, x);
            if (idx < 0) idx = -idx - 1;
            if (idx == dp.size()) {
                dp.add(x);
                sums.add((sums.isEmpty() ? 0 : sums.get(sums.size() - 1)) + x);
            } else {
                dp.set(idx, x);
                sums.set(idx, (idx > 0 ? sums.get(idx - 1) : 0) + x);
            }
        }
        return total - sums.get(sums.size() - 1);
    }
}
```

## Code (Python)

```python
import bisect
class Solution:
    def nonLisMaxSum(self, arr):
        dp, sums = [], []
        total = sum(arr)
        for x in arr:
            i = bisect.bisect_left(dp, x)
            if i == len(dp):
                dp.append(x)
                sums.append((sums[-1] if sums else 0) + x)
            else:
                dp[i] = x
                sums[i] = (sums[i-1] if i else 0) + x
        return total - sums[-1]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
