---
title: "📊 Longest Subarray with Majority Greater than K | GFG Solution 🔍"
keywords🏷️: ["📊 longest subarray", "🔍 prefix sum", "📍 hash map", "📈 majority element", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Longest Subarray with Majority Greater than K problem: find maximum length subarray where count of elements > k exceeds count of elements ≤ k using prefix sum technique. 🚀"
date: 📅 2025-08-02
---

# *214. Longest Subarray with Majority Greater than K*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/longest-subarray-with-majority-greater-than-k/1)

## **🧩 Problem Description**

You are given an array `arr[]` and an integer `k`. Your task is to find the length of the **longest subarray** in which the count of elements greater than `k` is **more than** the count of elements less than or equal to `k`.

A subarray is a contiguous sequence of elements within an array. The goal is to find the maximum possible length of such a subarray where elements > k have majority over elements ≤ k.


## Code(C++)
```cpp
class Solution {
public:
    int longestSubarray(vector<int>& arr, int k) {
        int n = arr.size(), ans = 0, sum = 0;
        unordered_map<int, int> mp;
        for (int i = 0; i < n; ++i) {
            sum += arr[i] <= k ? -1 : 1;
            if (sum > 0) ans = i + 1;
            else if (mp.count(sum - 1)) ans = max(ans, i - mp[sum - 1]);
            if (!mp.count(sum)) mp[sum] = i;
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int longestSubarray(int[] arr, int k) {
        int n = arr.length, ans = 0, sum = 0;
        Map<Integer, Integer> mp = new HashMap<>();
        for (int i = 0; i < n; ++i) {
            sum += (arr[i] > k) ? 1 : -1;
            if (sum > 0) ans = i + 1;
            else if (mp.containsKey(sum - 1)) ans = Math.max(ans, i - mp.get(sum - 1));
            mp.putIfAbsent(sum, i);
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def longestSubarray(self, arr, k):
        mp, ans, s = {0: -1}, 0, 0
        for i, x in enumerate(arr):
            s += -1 if x <= k else 1
            if s > 0: ans = i + 1
            elif s - 1 in mp: ans = max(ans, i - mp[s - 1])
            mp.setdefault(s, i)
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
