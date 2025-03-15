---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Dynamic Programming
---

# 🚀 _Day 74. Coin Change (Minimum Coins)_ 🧠

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/dynamic-programming-gfg-160/problem/number-of-coins1824)  

## 💡 **Problem Description:**

Given an array `coins[]` of distinct denominations and an integer `sum`, determine the **minimum number of coins** required to make up the given sum.  
You have **an infinite supply** of each type of coin.  
If the sum **cannot be formed**, return `-1`.  


## Code(C++)
```cpp
class Solution {
  public:
    int minCoins(vector<int>& coins, int sum) {
        vector<int> dp(sum + 1, INT_MAX);
        dp[0] = 0;
        for (int c : coins)
            for (int j = c; j <= sum; j++)
                if (dp[j - c] != INT_MAX)
                    dp[j] = min(dp[j], dp[j - c] + 1);
        return dp[sum] == INT_MAX ? -1 : dp[sum];
    }
};
```

## Code (Java)

```java
class Solution {
    public int minCoins(int[] coins, int sum) {
        int[] dp = new int[sum + 1];
        Arrays.fill(dp, Integer.MAX_VALUE);
        dp[0] = 0;
        for (int c : coins)
            for (int j = c; j <= sum; j++)
                if (dp[j - c] != Integer.MAX_VALUE)
                    dp[j] = Math.min(dp[j], dp[j - c] + 1);
        return dp[sum] == Integer.MAX_VALUE ? -1 : dp[sum];
    }
}
```

## Code (Python)

```python
class Solution:
    def minCoins(self, coins, sum):
        dp = [float('inf')] * (sum + 1)
        dp[0] = 0
        for c in coins:
            for j in range(c, sum + 1):
                dp[j] = min(dp[j], dp[j - c] + 1)
        return -1 if dp[sum] == float('inf') else dp[sum]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
