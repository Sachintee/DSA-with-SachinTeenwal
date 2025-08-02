--- ❤️ ---

# 🚀 _Day 214. Unique Paths in a Grid_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/unique-paths-in-a-grid/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int uniquePathsWithObstacles(vector<vector<int>> &A) {
        int m = A.size(), n = A[0].size();
        if (A[0][0] == 1) return 0;

        vector<vector<int>> dp(m, vector<int>(n, 0));
        dp[0][0] = 1;

        for (int i = 1; i < m; i++)
            if (A[i][0] == 0)
                dp[i][0] = dp[i-1][0];

        for (int j = 1; j < n; j++)
            if (A[0][j] == 0)
                dp[0][j] = dp[0][j-1];

        for (int i = 1; i < m; i++) {
            for (int j = 1; j < n; j++) {
                if (A[i][j] == 0)
                    dp[i][j] = dp[i-1][j] + dp[i][j-1];
            }
        }

        return dp[m-1][n-1];
    }
};

```

## Code (Java)

```java
public class Solution {
    public int uniquePathsWithObstacles(int[][] A) {
        int m = A.length, n = A[0].length;
        if (A[0][0] == 1) return 0;

        int[][] dp = new int[m][n];
        dp[0][0] = 1;

        for (int i = 1; i < m; i++)
            if (A[i][0] == 0)
                dp[i][0] = dp[i-1][0];

        for (int j = 1; j < n; j++)
            if (A[0][j] == 0)
                dp[0][j] = dp[0][j-1];

        for (int i = 1; i < m; i++) {
            for (int j = 1; j < n; j++) {
                if (A[i][j] == 0)
                    dp[i][j] = dp[i-1][j] + dp[i][j-1];
            }
        }

        return dp[m-1][n-1];
    }
}

```

## Code (Python)

```python
class Solution:
    def uniquePathsWithObstacles(self, A):
        m, n = len(A), len(A[0])
        if A[0][0] == 1:
            return 0

        dp = [[0] * n for _ in range(m)]
        dp[0][0] = 1

        # Fill first column
        for i in range(1, m):
            if A[i][0] == 0:
                dp[i][0] = dp[i-1][0]

        # Fill first row
        for j in range(1, n):
            if A[0][j] == 0:
                dp[0][j] = dp[0][j-1]

        # Fill rest of the grid
        for i in range(1, m):
            for j in range(1, n):
                if A[i][j] == 0:
                    dp[i][j] = dp[i-1][j] + dp[i][j-1]

        return dp[m-1][n-1]

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
