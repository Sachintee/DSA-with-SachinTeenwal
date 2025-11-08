---
title: "🎯 Number of Paths in a Matrix with K Coins | GFG Solution 🔍"
keywords🏷️: ["🎯 matrix paths", "🔍 dynamic programming", "📍 path counting", "📈 space optimization", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Number of Paths in a Matrix with K Coins problem: count paths from top-left to bottom-right collecting exactly k coins using optimized dynamic programming. 🚀"
date: 📅 2025-11-08
---

# *312. Number of Paths in a Matrix with K Coins*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/number-of-paths-in-a-matrix-with-k-coins2728/1)

## **🧩 Problem Description**

You are given a matrix `mat[][]` of size `n x m`, where each cell contains some coins. Your task is to count the number of ways to collect **exactly k coins** while moving from the **top-left cell** to the **bottom-right cell**.

From a cell `(i, j)`, you can only move to:
- Cell `(i+1, j)` (down)
- Cell `(i, j+1)` (right)

## Code(C++)
```cpp
class Solution {
public:
    int numberOfPath(vector<vector<int>>& mat, int k) {
        int n = mat.size(), m = mat[0].size();
        vector<vector<int>> dp(m, vector<int>(k + 1, 0));
        if (mat[0][0] <= k) dp[0][mat[0][0]] = 1;
        for (int j = 1; j < m; j++)
            for (int s = mat[0][j]; s <= k; s++)
                dp[j][s] = dp[j - 1][s - mat[0][j]];
        for (int i = 1; i < n; i++) {
            vector<vector<int>> ndp(m, vector<int>(k + 1, 0));
            if (mat[i][0] <= k)
                for (int s = mat[i][0]; s <= k; s++)
                    ndp[0][s] = dp[0][s - mat[i][0]];
            for (int j = 1; j < m; j++)
                for (int s = mat[i][j]; s <= k; s++)
                    ndp[j][s] = ndp[j - 1][s - mat[i][j]] + dp[j][s - mat[i][j]];
            dp = ndp;
        }
        return dp[m - 1][k];
    }
};
```

## Code (Java)

```java
class Solution {
    public int numberOfPath(int[][] mat, int k) {
        int n = mat.length, m = mat[0].length;
        int[][] dp = new int[m][k + 1];
        if (mat[0][0] <= k) dp[0][mat[0][0]] = 1;
        for (int j = 1; j < m; j++)
            for (int s = mat[0][j]; s <= k; s++)
                dp[j][s] = dp[j - 1][s - mat[0][j]];
        for (int i = 1; i < n; i++) {
            int[][] ndp = new int[m][k + 1];
            if (mat[i][0] <= k)
                for (int s = mat[i][0]; s <= k; s++)
                    ndp[0][s] = dp[0][s - mat[i][0]];
            for (int j = 1; j < m; j++)
                for (int s = mat[i][j]; s <= k; s++)
                    ndp[j][s] = ndp[j - 1][s - mat[i][j]] + dp[j][s - mat[i][j]];
            dp = ndp;
        }
        return dp[m - 1][k];
    }
}
```

## Code (Python)

```python
class Solution:
    def numberOfPath(self, mat, k):
        n, m = len(mat), len(mat[0])
        dp = [[0] * (k + 1) for _ in range(m)]
        if mat[0][0] <= k:
            dp[0][mat[0][0]] = 1
        for j in range(1, m):
            for s in range(mat[0][j], k + 1):
                dp[j][s] = dp[j - 1][s - mat[0][j]]
        for i in range(1, n):
            ndp = [[0] * (k + 1) for _ in range(m)]
            if mat[i][0] <= k:
                for s in range(mat[i][0], k + 1):
                    ndp[0][s] = dp[0][s - mat[i][0]]
            for j in range(1, m):
                for s in range(mat[i][j], k + 1):
                    ndp[j][s] = ndp[j - 1][s - mat[i][j]] + dp[j][s - mat[i][j]]
            dp = ndp
        return dp[m - 1][k]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
