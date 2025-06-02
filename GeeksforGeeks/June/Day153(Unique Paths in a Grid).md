---
title: "🚶 Unique Paths in a Grid | GFG Solution 🚧"
keywords🏷️: ["🚶 unique paths", "📊 dynamic programming", "🔄 DP", "📈 grid traversal", "📘 GFG", "🧩 obstacle grid", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Unique Paths in a Grid problem: count ways to traverse a grid with obstacles using optimized DP."
date: 📅 2025-06-02
---

# *152. Unique Paths in a Grid*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/unique-paths-in-a-grid--170647/1)

## **🧩 Problem Description**

You are given a 2D list `grid[][]` of size `n × m` consisting of values `0` and `1`.

* A value of `0` means that you can enter that cell.
* A value of `1` implies that entry to that cell is not allowed (an obstacle).

You start at the upper-left corner of the grid `(1, 1)` and you have to reach the bottom-right corner `(n, m)` by moving only **right** or **down** at each step.
Your task is to calculate the total number of ways to reach the target.

**Note:** The first `(1, 1)` and last `(n, m)` cells of the grid can also be `1`. It is guaranteed that the total number of ways will fit within a 32-bit integer.


## Code(C++)
```cpp
class Solution {
  public:
    int uniquePaths(vector<vector<int>> &grid) {
        int r = grid.size(), c = grid[0].size();
        vector<int> dp(c);
        dp[0] = grid[0][0] == 0;
        for (int i = 0; i < r; ++i)
            for (int j = 0; j < c; ++j)
                if (grid[i][j]) dp[j] = 0;
                else if (j) dp[j] += dp[j - 1];
        return dp[c - 1];
    }
};
```

## Code (Java)

```java
class Solution {
    public int uniquePaths(int[][] grid) {
        int r = grid.length, c = grid[0].length;
        int[] dp = new int[c];
        dp[0] = grid[0][0] == 0 ? 1 : 0;
        for (int i = 0; i < r; ++i)
            for (int j = 0; j < c; ++j)
                if (grid[i][j] == 1) dp[j] = 0;
                else if (j > 0) dp[j] += dp[j - 1];
        return dp[c - 1];
    }
}
```

## Code (Python)

```python
class Solution:
    def uniquePaths(self, grid):
        r, c = len(grid), len(grid[0])
        dp = [0] * c
        dp[0] = 1 if grid[0][0] == 0 else 0
        for i in range(r):
            for j in range(c):
                if grid[i][j] == 1:
                    dp[j] = 0
                elif j > 0:
                    dp[j] += dp[j - 1]
        return dp[-1]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
