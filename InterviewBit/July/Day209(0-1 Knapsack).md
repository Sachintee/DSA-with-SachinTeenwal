--- ❤️ ---

# 🚀 _Day 209. 0-1 Knapsack_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/0-1-knapsack/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <algorithm>
using namespace std;

class Solution {
public:
    int solve(vector<int> &A, vector<int> &B, int C) {
        int N = A.size();
        vector<vector<int>> dp(N + 1, vector<int>(C + 1, 0));

        for (int i = 1; i <= N; ++i) {
            for (int w = 0; w <= C; ++w) {
                if (B[i - 1] <= w) {
                    dp[i][w] = max(dp[i - 1][w], A[i - 1] + dp[i - 1][w - B[i - 1]]);
                } else {
                    dp[i][w] = dp[i - 1][w];
                }
            }
        }

        return dp[N][C];
    }
};

```

## Code (Java)

```java
public class Solution {
    public int solve(int[] A, int[] B, int C) {
        int N = A.length;
        int[][] dp = new int[N + 1][C + 1];

        for (int i = 1; i <= N; i++) {
            for (int w = 0; w <= C; w++) {
                if (B[i - 1] <= w) {
                    dp[i][w] = Math.max(dp[i - 1][w], A[i - 1] + dp[i - 1][w - B[i - 1]]);
                } else {
                    dp[i][w] = dp[i - 1][w];
                }
            }
        }

        return dp[N][C];
    }
}

```

## Code (Python)

```python
class Solution:
    # @param A : list of integers (values)
    # @param B : list of integers (weights)
    # @param C : integer (knapsack capacity)
    # @return an integer
    def solve(self, A, B, C):
        N = len(A)
        dp = [[0] * (C + 1) for _ in range(N + 1)]

        for i in range(1, N + 1):
            for w in range(C + 1):
                if B[i - 1] <= w:
                    dp[i][w] = max(dp[i - 1][w], A[i - 1] + dp[i - 1][w - B[i - 1]])
                else:
                    dp[i][w] = dp[i - 1][w]

        return dp[N][C]

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
