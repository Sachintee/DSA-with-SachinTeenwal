--- ❤️ ---

# 🚀 _Day 203. Shortest common superstring_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/shortest-common-superstring/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <string>
#include <algorithm>
using namespace std;

class Solution {
public:
    int solve(vector<string> &A) {
        int n = A.size();
        vector<vector<int>> overlap(n, vector<int>(n, 0));

        // Calculate overlaps
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                if (i != j) {
                    int max_ov = min(A[i].size(), A[j].size());
                    for (int k = max_ov; k >= 1; k--) {
                        if (A[i].substr(A[i].size() - k) == A[j].substr(0, k)) {
                            overlap[i][j] = k;
                            break;
                        }
                    }
                }
            }
        }

        // Initialize DP
        vector<vector<int>> dp(1 << n, vector<int>(n, 1e9));
        for (int i = 0; i < n; i++) {
            dp[1 << i][i] = A[i].size();
        }

        // DP transition
        for (int mask = 0; mask < (1 << n); mask++) {
            for (int last = 0; last < n; last++) {
                if (!(mask & (1 << last))) continue;
                for (int nex = 0; nex < n; nex++) {
                    if (mask & (1 << nex)) continue;
                    int new_mask = mask | (1 << nex);
                    dp[new_mask][nex] = min(dp[new_mask][nex],
                        dp[mask][last] + (int)A[nex].size() - overlap[last][nex]);
                }
            }
        }

        // Result: minimum of all ending points covering all strings
        int ans = 1e9;
        int full_mask = (1 << n) - 1;
        for (int i = 0; i < n; i++) {
            ans = min(ans, dp[full_mask][i]);
        }

        return ans;
    }
};

```

## Code (Java)

```java
public class Solution {
    public int solve(String[] A) {
        int n = A.length;
        int[][] overlap = new int[n][n];

        // Calculate overlaps
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                if (i != j) {
                    int max_ov = Math.min(A[i].length(), A[j].length());
                    for (int k = max_ov; k >= 1; k--) {
                        if (A[i].substring(A[i].length() - k).equals(A[j].substring(0, k))) {
                            overlap[i][j] = k;
                            break;
                        }
                    }
                }
            }
        }

        int[][] dp = new int[1 << n][n];
        for (int i = 0; i < (1 << n); i++) {
            for (int j = 0; j < n; j++) {
                dp[i][j] = Integer.MAX_VALUE / 2;
            }
        }

        // Initialize DP
        for (int i = 0; i < n; i++) {
            dp[1 << i][i] = A[i].length();
        }

        // DP transition
        for (int mask = 0; mask < (1 << n); mask++) {
            for (int last = 0; last < n; last++) {
                if ((mask & (1 << last)) == 0) continue;
                for (int nex = 0; nex < n; nex++) {
                    if ((mask & (1 << nex)) != 0) continue;
                    int new_mask = mask | (1 << nex);
                    dp[new_mask][nex] = Math.min(dp[new_mask][nex],
                        dp[mask][last] + A[nex].length() - overlap[last][nex]);
                }
            }
        }

        // Result: minimum of all ending points covering all strings
        int ans = Integer.MAX_VALUE;
        int full_mask = (1 << n) - 1;
        for (int i = 0; i < n; i++) {
            ans = Math.min(ans, dp[full_mask][i]);
        }

        return ans;
    }
}

```

## Code (Python)

```python
class Solution:
    # @param A : list of strings
    # @return an integer
    def solve(self, A):
        from functools import lru_cache

        n = len(A)

        # Calculate overlaps
        overlap = [[0]*n for _ in range(n)]
        for i in range(n):
            for j in range(n):
                if i != j:
                    max_ov = min(len(A[i]), len(A[j]))
                    for k in range(max_ov, 0, -1):
                        if A[i].endswith(A[j][:k]):
                            overlap[i][j] = k
                            break

        # Initialize DP
        dp = [[float('inf')]*n for _ in range(1<<n)]
        for i in range(n):
            dp[1<<i][i] = len(A[i])

        # Fill DP table
        for mask in range(1<<n):
            for last in range(n):
                if not (mask & (1<<last)):
                    continue
                for nex in range(n):
                    if mask & (1<<nex):
                        continue
                    new_mask = mask | (1<<nex)
                    dp[new_mask][nex] = min(dp[new_mask][nex],
                                            dp[mask][last] + len(A[nex]) - overlap[last][nex])

        # Result: minimum of all ending points covering all strings
        full_mask = (1<<n) - 1
        return min(dp[full_mask][i] for i in range(n))

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
