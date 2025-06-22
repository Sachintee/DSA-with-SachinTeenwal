---
title: "🧩 Largest Divisible Subset | GFG Solution 📊"
keywords🏷️: ["🧩 largest divisible subset", "🔍 dynamic programming", "📍 subset", "📈 divisibility", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Largest Divisible Subset problem: find the largest subset where every pair divides each other using dynamic programming. 🚀"
date: 📅 2025-06-22
---

# *173. Largest Divisible Subset*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/largest-divisible-subset--170643/1)

## **🧩 Problem Description**

Given an array `arr[]` of distinct positive integers, find the **largest subset** such that for every pair of elements `(x, y)` in the subset, either `x` divides `y` or `y` divides `x`.

**Note:** If multiple subsets of the same maximum length exist, return the one that is **lexicographically greatest** after sorting the subset in ascending order.


## Code(C++)
```cpp
class Solution {
public:
    vector<int> largestSubset(vector<int>& arr) {
        int n = arr.size();
        sort(arr.rbegin(), arr.rend());
        vector<int> dp(n, 1), parent(n, -1);
        int maxIdx = 0;
        
        for (int i = 1; i < n; i++) {
            for (int j = 0; j < i; j++) {
                if (arr[j] % arr[i] == 0 && dp[j] + 1 > dp[i]) {
                    dp[i] = dp[j] + 1;
                    parent[i] = j;
                }
            }
            if (dp[i] > dp[maxIdx]) maxIdx = i;
        }
        
        vector<int> result;
        for (int i = maxIdx; i != -1; i = parent[i]) {
            result.push_back(arr[i]);
        }
        return result;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<Integer> largestSubset(int[] arr) {
        int n = arr.length;
        Integer[] temp = new Integer[n];
        for (int i = 0; i < n; i++) temp[i] = arr[i];
        Arrays.sort(temp, Collections.reverseOrder());
        
        int[] dp = new int[n];
        int[] parent = new int[n];
        Arrays.fill(dp, 1);
        Arrays.fill(parent, -1);
        
        int maxIdx = 0;
        for (int i = 1; i < n; i++) {
            for (int j = 0; j < i; j++) {
                if (temp[j] % temp[i] == 0 && dp[j] + 1 > dp[i]) {
                    dp[i] = dp[j] + 1;
                    parent[i] = j;
                }
            }
            if (dp[i] > dp[maxIdx]) maxIdx = i;
        }
        
        ArrayList<Integer> result = new ArrayList<>();
        for (int i = maxIdx; i != -1; i = parent[i]) {
            result.add(temp[i]);
        }
        return result;
    }
}
```

## Code (Python)

```python
class Solution:
    def largestSubset(self, arr):
        n = len(arr)
        arr.sort(reverse=True)
        dp = [1] * n
        parent = [-1] * n
        max_idx = 0
        for i in range(1, n):
            for j in range(i):
                if arr[j] % arr[i] == 0 and dp[j] + 1 > dp[i]:
                    dp[i] = dp[j] + 1
                    parent[i] = j
            if dp[i] > dp[max_idx]:
                max_idx = i
        result = []
        i = max_idx
        while i != -1:
            result.append(arr[i])
            i = parent[i]
        return result
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
