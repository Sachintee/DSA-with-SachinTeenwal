---
title: "🔢 Subarrays With At Most K Distinct Integers | GFG Solution 🔍"
keywords🏷️: ["🔢 subarrays", "🔍 sliding window", "📍 two pointers", "📈 hash map", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Subarrays With At Most K Distinct Integers problem: count subarrays containing at most k distinct elements using sliding window technique. 🚀"
date: 📅 2025-07-04
---

# *185. Subarrays With At Most K Distinct Integers*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/subarrays-with-at-most-k-distinct-integers/1)

## **🧩 Problem Description**

You are given an array `arr[]` of positive integers and an integer `k`. Your task is to find the number of **subarrays** in `arr[]` where the count of distinct integers is **at most k**.

A subarray is a contiguous part of an array. The goal is to efficiently count all valid subarrays without generating them explicitly.


## Code(C++)
```cpp
class Solution {
public:
    int countAtMostK(vector<int> &arr, int k) {
        int n = arr.size(), res = 0, left = 0;
        unordered_map<int, int> freq;
        for (int right = 0; right < n; right++) {
            if (freq[arr[right]]++ == 0) k--;
            while (k < 0) {
                if (--freq[arr[left]] == 0) k++;
                left++;
            }
            res += right - left + 1;
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public int countAtMostK(int arr[], int k) {
        HashMap<Integer, Integer> freq = new HashMap<>();
        int n = arr.length, res = 0, left = 0;
        for (int right = 0; right < n; right++) {
            freq.put(arr[right], freq.getOrDefault(arr[right], 0) + 1);
            while (freq.size() > k) {
                freq.put(arr[left], freq.get(arr[left]) - 1);
                if (freq.get(arr[left]) == 0) freq.remove(arr[left]);
                left++;
            }
            res += right - left + 1;
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def countAtMostK(self, arr, k):
        freq = {}
        n, res, left = len(arr), 0, 0
        for right in range(n):
            freq[arr[right]] = freq.get(arr[right], 0) + 1
            while len(freq) > k:
                freq[arr[left]] -= 1
                if freq[arr[left]] == 0:
                    del freq[arr[left]]
                left += 1
            res += right - left + 1
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
