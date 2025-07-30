---
title: "➕ Subarrays with Sum K | GFG Solution 🔍"
keywords🏷️: ["➕ subarray sum", "🔍 prefix sum", "📍 hash map", "📈 cumulative sum", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Subarrays with Sum K problem: count number of subarrays with exact sum K using prefix sum and hash map technique. 🚀"
date: 📅 2025-07-30
---

# *211. Subarrays with Sum K*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/subarrays-with-sum-k/1)

## **🧩 Problem Description**

You are given an unsorted array `arr[]` of integers and a target sum `k`. Your task is to find the **number of subarrays** whose sum is exactly equal to the given number `k`.

A subarray is a contiguous sequence of elements within an array. The goal is to count all possible subarrays where the sum of elements equals the target value `k`.


## Code(C++)
```cpp
class Solution {
public:
    int cntSubarrays(vector<int>& arr, int k) {
        unordered_map<int, int> mp;
        int sum = 0, cnt = 0;
        mp[0] = 1;
        for (int x : arr) {
            sum += x;
            cnt += mp[sum - k];
            mp[sum]++;
        }
        return cnt;
    }
};
```

## Code (Java)

```java
class Solution {
    public int cntSubarrays(int[] arr, int k) {
        Map<Integer, Integer> map = new HashMap<>();
        int sum = 0, count = 0;
        map.put(0, 1);
        for (int num : arr) {
            sum += num;
            count += map.getOrDefault(sum - k, 0);
            map.merge(sum, 1, Integer::sum);
        }
        return count;
    }
}
```

## Code (Python)

```python
class Solution:
    def cntSubarrays(self, arr, k):
        mp, s, cnt = {0: 1}, 0, 0
        for x in arr:
            s += x
            cnt += mp.get(s - k, 0)
            mp[s] = mp.get(s, 0) + 1
        return cnt
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
