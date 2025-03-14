---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Dynamic Programming
  - Arrays
---

# 🚀 _Day 73. Coin Change (Count Ways)_ 🧠

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/dynamic-programming-gfg-160/problem/coin-change2448)  

## 💡 **Problem Description:**

Given an integer array **coins[]** representing different denominations of currency and an integer **sum**, find the **number of ways** to make `sum` using any number of coins.  
🔹 **Note:** You have an **infinite** supply of each type of coin.  


## Code(C++)
```cpp
class Solution {
  public:
    int count(vector<int>& coins, int sum) {
        vector<int> dp(sum + 1, 0);
        dp[0] = 1;
        for (int coin : coins)
            for (int j = coin; j <= sum; j++)
                dp[j] += dp[j - coin];
        return dp[sum];
    }
};
```

## Code (Java)

```java
class Solution {
    public int count(int[] coins, int sum) {
        int[] dp = new int[sum + 1];
        dp[0] = 1;
        for (int coin : coins)
            for (int j = coin; j <= sum; j++)
                dp[j] += dp[j - coin];
        return dp[sum];
    }
}
```

## Code (Python)

```python
class Solution:
    def count(self, coins, sum):
        dp = [0] * (sum + 1)
        dp[0] = 1
        for coin in coins:
            for j in range(coin, sum + 1):
                dp[j] += dp[j - coin]
        return dp[sum]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
