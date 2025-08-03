--- ❤️ ---

# 🚀 _Day 215. Interleaving Strings_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/interleaving-strings/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int isInterleave(string A, string B, string C) {
        int n = A.size(), m = B.size(), l = C.size();
        if (n + m != l) return 0;

        vector<vector<bool>> dp(n + 1, vector<bool>(m + 1, false));
        dp[0][0] = true;

        for (int i = 0; i <= n; ++i) {
            for (int j = 0; j <= m; ++j) {
                if (i > 0 && A[i - 1] == C[i + j - 1])
                    dp[i][j] = dp[i][j] || dp[i - 1][j];
                if (j > 0 && B[j - 1] == C[i + j - 1])
                    dp[i][j] = dp[i][j] || dp[i][j - 1];
            }
        }

        return dp[n][m] ? 1 : 0;
    }
};

```

## Code (Java)

```java
public class Solution {
    public int isInterleave(String A, String B, String C) {
        int n = A.length(), m = B.length(), l = C.length();
        if (n + m != l) return 0;

        boolean[][] dp = new boolean[n + 1][m + 1];
        dp[0][0] = true;

        for (int i = 0; i <= n; i++) {
            for (int j = 0; j <= m; j++) {
                if (i > 0 && A.charAt(i - 1) == C.charAt(i + j - 1))
                    dp[i][j] |= dp[i - 1][j];
                if (j > 0 && B.charAt(j - 1) == C.charAt(i + j - 1))
                    dp[i][j] |= dp[i][j - 1];
            }
        }

        return dp[n][m] ? 1 : 0;
    }
}

```

## Code (Python)

```python
class Solution:
    def isInterleave(self, A, B, C):
        n, m, l = len(A), len(B), len(C)
        if n + m != l:
            return 0

        dp = [[False] * (m + 1) for _ in range(n + 1)]
        dp[0][0] = True

        for i in range(n + 1):
            for j in range(m + 1):
                if i > 0 and A[i-1] == C[i+j-1]:
                    dp[i][j] |= dp[i-1][j]
                if j > 0 and B[j-1] == C[i+j-1]:
                    dp[i][j] |= dp[i][j-1]

        return int(dp[n][m])

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
