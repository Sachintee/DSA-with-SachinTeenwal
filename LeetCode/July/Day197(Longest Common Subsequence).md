--- ❤️ ---

# 🚀 _Day 197. Longest Common Subsequence_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/longest-common-subsequence/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int solve(string A, string B) {
        int n = A.size();
        int m = B.size();
        vector<vector<int>> dp(n+1, vector<int>(m+1, 0));

        for (int i = 1; i <= n; ++i) {
            for (int j = 1; j <= m; ++j) {
                if (A[i-1] == B[j-1])
                    dp[i][j] = 1 + dp[i-1][j-1];
                else
                    dp[i][j] = max(dp[i-1][j], dp[i][j-1]);
            }
        }

        return dp[n][m];
    }
};

```

## Code (Java)

```java
public class Solution {
    public int solve(String A, String B) {
        int n = A.length();
        int m = B.length();
        int[][] dp = new int[n+1][m+1];

        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= m; j++) {
                if (A.charAt(i-1) == B.charAt(j-1)) {
                    dp[i][j] = 1 + dp[i-1][j-1];
                } else {
                    dp[i][j] = Math.max(dp[i-1][j], dp[i][j-1]);
                }
            }
        }

        return dp[n][m];
    }
}

```

## Code (Python)

```python
class Solution:
    # @param A : string
    # @param B : string
    # @return an integer
    def solve(self, A, B):
        n = len(A)
        m = len(B)

        dp = [[0]*(m+1) for _ in range(n+1)]

        for i in range(1, n+1):
            for j in range(1, m+1):
                if A[i-1] == B[j-1]:
                    dp[i][j] = 1 + dp[i-1][j-1]
                else:
                    dp[i][j] = max(dp[i-1][j], dp[i][j-1])

        return dp[n][m]

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
