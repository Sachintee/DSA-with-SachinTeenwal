---
title: "🪨 Minimum Cost to Merge Stones | GFG Solution 🔍"
keywords🏷️: ["🪨 merge stones", "🔍 dynamic programming", "📍 interval dp", "📈 prefix sum", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Minimum Cost to Merge Stones problem: find minimum cost to merge all stone piles into one using dynamic programming with interval DP technique. 🚀"
date: 📅 2025-11-14
---

# *318. Minimum Cost to Merge Stones*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/minimum-cost-to-merge-stones/1)

## **🧩 Problem Description**

You are given an array `stones[]`, where the ith element represents the number of stones in the ith pile. In one move, you can merge exactly **k consecutive piles** into a single pile, and the cost of this move is equal to the total number of stones in these k piles.

Determine the **minimum total cost** required to merge all the piles into one single pile. If it is not possible to merge all piles into one according to the given rules, return **-1**.


## Code(C++)
```cpp
class Solution {
public:
    int mergeStones(vector<int>& stones, int k) {
        int n = stones.size();
        if ((n - 1) % (k - 1)) return -1;
        vector<int> sum(n + 1);
        for (int i = 0; i < n; i++) sum[i + 1] = sum[i] + stones[i];
        vector<vector<int>> dp(n, vector<int>(n));
        for (int len = k; len <= n; len++) {
            for (int i = 0; i + len <= n; i++) {
                int j = i + len - 1;
                dp[i][j] = INT_MAX;
                for (int mid = i; mid < j; mid += k - 1)
                    dp[i][j] = min(dp[i][j], dp[i][mid] + dp[mid + 1][j]);
                if ((j - i) % (k - 1) == 0)
                    dp[i][j] += sum[j + 1] - sum[i];
            }
        }
        return dp[0][n - 1];
    }
};
```

## Code (Java)

```java
class Solution {
    public int mergeStones(int[] stones, int k) {
        int n = stones.length;
        if ((n - 1) % (k - 1) != 0) return -1;
        int[] sum = new int[n + 1];
        for (int i = 0; i < n; i++) sum[i + 1] = sum[i] + stones[i];
        int[][] dp = new int[n][n];
        for (int len = k; len <= n; len++) {
            for (int i = 0; i + len <= n; i++) {
                int j = i + len - 1;
                dp[i][j] = Integer.MAX_VALUE;
                for (int mid = i; mid < j; mid += k - 1)
                    dp[i][j] = Math.min(dp[i][j], dp[i][mid] + dp[mid + 1][j]);
                if ((j - i) % (k - 1) == 0)
                    dp[i][j] += sum[j + 1] - sum[i];
            }
        }
        return dp[0][n - 1];
    }
}
```

## Code (Python)

```python
class Solution:
    def mergeStones(self, stones, k):
        n = len(stones)
        if (n - 1) % (k - 1): return -1
        s = [0] * (n + 1)
        for i in range(n): s[i + 1] = s[i] + stones[i]
        dp = [[0] * n for _ in range(n)]
        for l in range(k, n + 1):
            for i in range(n - l + 1):
                j = i + l - 1
                dp[i][j] = float('inf')
                for m in range(i, j, k - 1):
                    dp[i][j] = min(dp[i][j], dp[i][m] + dp[m + 1][j])
                if (j - i) % (k - 1) == 0:
                    dp[i][j] += s[j + 1] - s[i]
        return dp[0][n - 1]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
