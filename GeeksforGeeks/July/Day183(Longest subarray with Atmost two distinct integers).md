---
title: "🔢 Longest Subarray with At Most Two Distinct Integers | GFG Solution 🔍"
keywords🏷️: ["🔢 longest subarray", "🔍 sliding window", "📍 two pointers", "📈 hash map", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Longest Subarray with At Most Two Distinct Integers problem: find maximum length subarray containing at most 2 distinct elements using sliding window technique. 🚀"
date: 📅 2025-07-02
---

# *183. Longest Subarray with At Most Two Distinct Integers*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/fruit-into-baskets-1663137462/1)

## **🧩 Problem Description**

You are given an array `arr[]` consisting of positive integers. Your task is to find the length of the **longest subarray** that contains **at most two distinct integers**.

A subarray is a contiguous sequence of elements within an array. The goal is to find the maximum possible length of such a subarray where the number of unique elements does not exceed 2.


## Code(C++)
```cpp
class Solution {
public:
    int totalElements(vector<int> &arr) {
        unordered_map<int, int> mp;
        int i = 0, maxLen = 0;
        for (int j = 0; j < arr.size(); j++) {
            mp[arr[j]]++;
            while (mp.size() > 2) {
                if (--mp[arr[i]] == 0) mp.erase(arr[i]);
                i++;
            }
            maxLen = max(maxLen, j - i + 1);
        }
        return maxLen;
    }
};
```

## Code (Java)

```java
class Solution {
    public int totalElements(int[] arr) {
        Map<Integer, Integer> map = new HashMap<>();
        int i = 0, max = 0;
        for (int j = 0; j < arr.length; j++) {
            map.put(arr[j], map.getOrDefault(arr[j], 0) + 1);
            while (map.size() > 2) {
                map.put(arr[i], map.get(arr[i]) - 1);
                if (map.get(arr[i]) == 0) map.remove(arr[i]);
                i++;
            }
            max = Math.max(max, j - i + 1);
        }
        return max;
    }
}
```

## Code (Python)

```python
class Solution:
    def totalElements(self, arr):
        mp = {}
        i = maxLen = 0
        for j in range(len(arr)):
            mp[arr[j]] = mp.get(arr[j], 0) + 1
            while len(mp) > 2:
                mp[arr[i]] -= 1
                if mp[arr[i]] == 0:
                    del mp[arr[i]]
                i += 1
            maxLen = max(maxLen, j - i + 1)
        return maxLen
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
