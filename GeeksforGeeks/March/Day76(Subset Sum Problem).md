---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Dynamic Programming
---

# 🚀 _Day 76. Subset Sum Problem_ 🧠

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/dynamic-programming-gfg-160/problem/subset-sum-problem-1611555638)  


## 💡 **Problem Description:**

Given an array of positive integers **arr[]** and a target value **sum**, determine if there exists a **subset** of `arr[]` whose sum is exactly equal to the given sum.  


## Code(C++)
```cpp
class Solution {
  public:
    bool isSubsetSum(vector<int>& arr, int sum) {
        vector<bool> dp(sum + 1, false);
        dp[0] = true;
        for (int num : arr)
            for (int j = sum; j >= num; --j)
                dp[j] = dp[j] || dp[j - num];
        return dp[sum];
    }
};
```

## Code (Java)

```java
class Solution {
    static boolean isSubsetSum(int[] arr, int sum) {
        boolean[] dp = new boolean[sum + 1];
        dp[0] = true;
        for (int num : arr)
            for (int j = sum; j >= num; --j)
                dp[j] |= dp[j - num];
        return dp[sum];
    }
}
```

## Code (Python)

```python
class Solution:
    def isSubsetSum(self, arr, sum):
        dp = [False] * (sum + 1)
        dp[0] = True
        for num in arr:
            for j in range(sum, num - 1, -1):
                dp[j] |= dp[j - num]
        return dp[sum]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
