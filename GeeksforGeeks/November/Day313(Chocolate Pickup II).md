---
title: "🍫 Chocolate Pickup II | GFG Solution 🤖"
keywords🏷️: ["🍫 chocolate pickup", "🤖 two robots", "📍 dynamic programming", "📈 memoization", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Chocolate Pickup II problem: maximize chocolates collected by a robot traveling to bottom-right and back to top-left using optimal path selection with DP. 🚀"
date: 📅 2025-11-09
---

# *313. Chocolate Pickup II*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/chocolate-pickup-ii/1)

## **🧩 Problem Description**

You are given a square matrix `mat[][]` of size `n × n`, where each cell represents either a blocked cell or a cell containing some chocolates. If `mat[i][j]` equals `-1`, then the cell is blocked and cannot be visited. Otherwise, `mat[i][j]` represents the number of chocolates present in that cell.

The task is to determine the **maximum number of chocolates** a robot can collect by:
1. Starting from the top-left cell `(0, 0)`
2. Moving to the bottom-right cell `(n-1, n-1)`
3. Returning back to `(0, 0)`


## Code(C++)
```cpp
class Solution {
public:
    int chocolatePickup(vector<vector<int>>& mat) {
        int n = mat.size(), m = mat[0].size();
        vector<vector<vector<int>>> dp(n, vector<vector<int>>(m, vector<int>(m, -1)));
        function<int(int,int,int)> solve = [&](int i1, int j1, int j2) -> int {
            int i2 = i1 + j1 - j2;
            if (i1 >= n || i2 >= n || j1 >= m || j2 >= m || i2 < 0) return -1e8;
            if (mat[i1][j1] == -1 || mat[i2][j2] == -1) return -1e8;
            if (i1 == n - 1 && j1 == m - 1 && j2 == m - 1) return mat[i1][j1];
            if (dp[i1][j1][j2] != -1) return dp[i1][j1][j2];
            int res = -1e8;
            for (int d1 = 0; d1 < 2; d1++)
                for (int d2 = 0; d2 < 2; d2++)
                    res = max(res, solve(i1 + 1 - d1, j1 + d1, j2 + d2));
            res += mat[i1][j1];
            if (i1 != i2) res += mat[i2][j2];
            return dp[i1][j1][j2] = res;
        };
        return max(0, solve(0, 0, 0));
    }
};
```

## Code (Java)

```java
class Solution {
    int[][][] dp;
    int[][] mat;
    int n, m;
    
    int solve(int i1, int j1, int j2) {
        int i2 = i1 + j1 - j2;
        if (i1 >= n || i2 >= n || j1 >= m || j2 >= m || i2 < 0) return (int)-1e8;
        if (mat[i1][j1] == -1 || mat[i2][j2] == -1) return (int)-1e8;
        if (i1 == n - 1 && j1 == m - 1 && j2 == m - 1) return mat[i1][j1];
        if (dp[i1][j1][j2] != -1) return dp[i1][j1][j2];
        int res = (int)-1e8;
        for (int d1 = 0; d1 < 2; d1++)
            for (int d2 = 0; d2 < 2; d2++)
                res = Math.max(res, solve(i1 + 1 - d1, j1 + d1, j2 + d2));
        res += mat[i1][j1];
        if (i1 != i2) res += mat[i2][j2];
        return dp[i1][j1][j2] = res;
    }
    
    public int chocolatePickup(int[][] mat) {
        this.mat = mat;
        n = mat.length;
        m = mat[0].length;
        dp = new int[n][m][m];
        for (int[][] a : dp) for (int[] b : a) Arrays.fill(b, -1);
        return Math.max(0, solve(0, 0, 0));
    }
}
```

## Code (Python)

```python
class Solution: 
    def chocolatePickup(self, mat): 
        n, m = len(mat), len(mat[0])
        dp = [[[-1] * m for _ in range(m)] for _ in range(n)]
        
        def solve(i1, j1, j2):
            i2 = i1 + j1 - j2
            if i1 >= n or i2 >= n or j1 >= m or j2 >= m or i2 < 0:
                return -10**8
            if mat[i1][j1] == -1 or mat[i2][j2] == -1:
                return -10**8
            if i1 == n - 1 and j1 == m - 1 and j2 == m - 1:
                return mat[i1][j1]
            if dp[i1][j1][j2] != -1:
                return dp[i1][j1][j2]
            res = -10**8
            for d1 in range(2):
                for d2 in range(2):
                    res = max(res, solve(i1 + 1 - d1, j1 + d1, j2 + d2))
            res += mat[i1][j1]
            if i1 != i2:
                res += mat[i2][j2]
            dp[i1][j1][j2] = res
            return res
        
        return max(0, solve(0, 0, 0))
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
