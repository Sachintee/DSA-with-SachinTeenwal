--- ❤️ ---

# 🚀 _Day 217. Dungeon Princess_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/dungeon-princess/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int calculateMinimumHP(vector<vector<int>>& A) {
        int M = A.size();
        int N = A[0].size();
        vector<vector<int>> dp(M + 1, vector<int>(N + 1, INT_MAX));

        // Dummy cells
        dp[M][N - 1] = dp[M - 1][N] = 1;

        for (int i = M - 1; i >= 0; i--) {
            for (int j = N - 1; j >= 0; j--) {
                int minNext = min(dp[i + 1][j], dp[i][j + 1]);
                dp[i][j] = max(1, minNext - A[i][j]);
            }
        }

        return dp[0][0];
    }
};

```

## Code (Java)

```java
public class Solution {
    public int calculateMinimumHP(int[][] A) {
        int M = A.length;
        int N = A[0].length;
        int[][] dp = new int[M + 1][N + 1];

        // Fill with max value
        for (int i = 0; i <= M; i++) {
            for (int j = 0; j <= N; j++) {
                dp[i][j] = Integer.MAX_VALUE;
            }
        }

        // Dummy cells beyond the bottom and right edge
        dp[M][N - 1] = dp[M - 1][N] = 1;

        for (int i = M - 1; i >= 0; i--) {
            for (int j = N - 1; j >= 0; j--) {
                int minNext = Math.min(dp[i + 1][j], dp[i][j + 1]);
                dp[i][j] = Math.max(1, minNext - A[i][j]);
            }
        }

        return dp[0][0];
    }
}

```

## Code (Python)

```python
class Solution:
    def calculateMinimumHP(self, A):
        M, N = len(A), len(A[0])
        dp = [[float('inf')] * (N+1) for _ in range(M+1)]
        
        dp[M][N-1] = dp[M-1][N] = 1  # Dummy boundary values to simplify bottom-right

        for i in range(M-1, -1, -1):
            for j in range(N-1, -1, -1):
                min_health_needed = min(dp[i+1][j], dp[i][j+1]) - A[i][j]
                dp[i][j] = max(1, min_health_needed)

        return dp[0][0]

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
