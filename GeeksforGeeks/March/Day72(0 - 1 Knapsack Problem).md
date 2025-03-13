---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Dynamic Programming
---

# 🚀 _Day 72. 0 - 1 Knapsack Problem_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/dynamic-programming-gfg-160/problem/0-1-knapsack-problem0945)  

## 💡 **Problem Description:**

Given `n` items, each with a **weight** and **value**, and a knapsack with a capacity of `W`, the task is to determine the maximum total value that can be obtained by placing items in the knapsack **without exceeding its weight capacity**.  

## Code(C++)
```cpp
class Solution {
  public:
    int knapsack(int W, vector<int> &val, vector<int> &wt) {
        vector<int> dp(W + 1);
        for (int i = 0; i < wt.size(); i++)
            for (int j = W; j >= wt[i]; j--)
                dp[j] = max(dp[j], val[i] + dp[j - wt[i]]);
        return dp[W];
    }
};
```

## Code (Java)

```java
class Solution {
    static int knapsack(int W, int[] val, int[] wt) {
        int[] dp = new int[W + 1];
        for (int i = 0; i < wt.length; i++) 
            for (int j = W; j >= wt[i]; j--) 
                dp[j] = Math.max(dp[j], val[i] + dp[j - wt[i]]);
        return dp[W];
    }
}
```

## Code (Python)

```python
class Solution:
    def knapsack(self, W, val, wt):
        dp = [0] * (W + 1)
        for i in range(len(wt)):
            for j in range(W, wt[i] - 1, -1):
                dp[j] = max(dp[j], val[i] + dp[j - wt[i]])
        return dp[W]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
