--- ❤️ ---

# 🚀 _Day 212. Maximum Size Square Sub-matrix_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/maximum-size-square-sub-matrix/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int solve(vector<vector<int>> &A) {
        int n = A.size(), m = A[0].size();
        vector<vector<int>> dp(n, vector<int>(m, 0));
        int maxSide = 0;

        for (int i = 0; i < n; i++) {
            for (int j = 0; j < m; j++) {
                if (A[i][j] == 1) {
                    if (i == 0 || j == 0)
                        dp[i][j] = 1;
                    else
                        dp[i][j] = 1 + min({dp[i-1][j], dp[i][j-1], dp[i-1][j-1]});
                    maxSide = max(maxSide, dp[i][j]);
                }
            }
        }
        return maxSide * maxSide;
    }
};

```

## Code (Java)

```java
public class Solution {
    public int solve(int[][] A) {
        int n = A.length;
        int m = A[0].length;
        int[][] dp = new int[n][m];
        int maxSide = 0;

        for (int i = 0; i < n; i++) {
            for (int j = 0; j < m; j++) {
                if (A[i][j] == 1) {
                    if (i == 0 || j == 0)
                        dp[i][j] = 1;
                    else
                        dp[i][j] = 1 + Math.min(dp[i-1][j], 
                                         Math.min(dp[i][j-1], dp[i-1][j-1]));
                    maxSide = Math.max(maxSide, dp[i][j]);
                }
            }
        }
        return maxSide * maxSide;
    }
}

```

## Code (Python)

```python
class Solution:
    def solve(self, A):
        if not A: return 0
        n, m = len(A), len(A[0])
        dp = [[0] * m for _ in range(n)]
        max_side = 0

        for i in range(n):
            for j in range(m):
                if A[i][j] == 1:
                    if i == 0 or j == 0:
                        dp[i][j] = 1
                    else:
                        dp[i][j] = 1 + min(dp[i-1][j], dp[i][j-1], dp[i-1][j-1])
                    max_side = max(max_side, dp[i][j])
        return max_side * max_side

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
