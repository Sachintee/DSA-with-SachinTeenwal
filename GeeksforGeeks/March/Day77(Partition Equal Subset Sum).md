---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Dynamic Programming
  - Subset
---

# 🚀 _Day 77. Partition Equal Subset Sum_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/dynamic-programming-gfg-160/problem/subset-sum-problem2014)  

## 💡 **Problem Description:**

Given an array `arr[]`, determine if it can be **partitioned into two subsets** such that the sum of elements in both parts is the same.  

Each element must be in exactly **one subset**.  


## Code(C++)
```cpp
class Solution {
  public:
    bool equalPartition(vector<int>& arr) {
        int sum = accumulate(arr.begin(), arr.end(), 0);
        if (sum % 2) return false;
        int target = sum / 2;
        vector<bool> dp(target + 1, false);
        dp[0] = true;
        for (int num : arr)
            for (int j = target; j >= num; --j)
                dp[j] = dp[j] || dp[j - num];
        return dp[target];
    }
};
```

## Code (Java)

```java
class Solution {
    static boolean equalPartition(int[] arr) {
        int sum = Arrays.stream(arr).sum();
        if (sum % 2 != 0) return false;
        int target = sum / 2;
        boolean[] dp = new boolean[target + 1];
        dp[0] = true;
        for (int num : arr)
            for (int j = target; j >= num; --j)
                dp[j] |= dp[j - num];
        return dp[target];
    }
}
```

## Code (Python)

```python
class Solution:
    def equalPartition(self, arr):
        s = sum(arr)
        if s % 2: return False
        target, dp = s // 2, [False] * (s // 2 + 1)
        dp[0] = True
        for num in arr:
            for j in range(target, num - 1, -1):
                dp[j] |= dp[j - num]
        return dp[target]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
