---
Difficulty: Hard  
Source: 160 Days of Problem Solving  
Tags:
  - Dynamic Programming
---

# 🚀 _Day 78. Stock Buy and Sell – Max K Transactions Allowed_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/dynamic-programming-gfg-160/problem/maximum-profit4657)  

## 💡 **Problem Description:**

In the stock market, a person can buy a stock and sell it on a future date. You are given an array **prices[]** representing stock prices on different days and a positive integer **k**.  

Find out the **maximum profit** a person can make with **at most k transactions**.  

A **transaction** consists of **buying** and subsequently **selling** a stock. A new transaction can only start after completing the previous one.  


## Code(C++)
```cpp
class Solution {
  public:
    int maxProfit(vector<int>& prices, int k) {
        int n = prices.size();
        if (n == 0 || k == 0) return 0;
        if (2 * k >= n) {
            int profit = 0;
            for (int i = 1; i < n; i++)
                profit += max(0, prices[i] - prices[i - 1]);
            return profit;
        }
        vector<int> dp(2 * k + 1, INT_MIN);
        dp[0] = 0;
        for (int price : prices)
            for (int j = 1; j <= 2 * k; j++)
                dp[j] = j % 2 ? max(dp[j], dp[j - 1] - price) : max(dp[j], dp[j - 1] + price);
        return dp[2 * k];
    }
};
```

## Code (Java)

```java
class Solution {
    public static int maxProfit(int[] prices, int k) {
        int n = prices.length;
        if (n == 0 || k == 0) return 0;
        if (2 * k >= n) {
            int profit = 0;
            for (int i = 1; i < n; i++)
                profit += Math.max(0, prices[i] - prices[i - 1]);
            return profit;
        }
        int[] dp = new int[2 * k + 1];
        Arrays.fill(dp, Integer.MIN_VALUE);
        dp[0] = 0;
        for (int price : prices)
            for (int j = 1; j <= 2 * k; j++)
                dp[j] = (j % 2 == 1) ? Math.max(dp[j], dp[j - 1] - price) : Math.max(dp[j], dp[j - 1] + price);
        return dp[2 * k];
    }
}
```

## Code (Python)

```python
class Solution:
    def maxProfit(self, prices, k):
        n = len(prices)
        if n == 0 or k == 0:
            return 0
        if 2 * k >= n:
            return sum(max(0, prices[i] - prices[i - 1]) for i in range(1, n))
        dp = [-float('inf')] * (2 * k + 1)
        dp[0] = 0
        for price in prices:
            for j in range(1, 2 * k + 1):
                dp[j] = max(dp[j], dp[j - 1] - price) if j % 2 else max(dp[j], dp[j - 1] + price)
        return dp[2 * k]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
