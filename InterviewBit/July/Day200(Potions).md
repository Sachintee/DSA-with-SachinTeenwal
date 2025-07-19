--- ❤️ ---

# 🚀 _Day 200. Potions_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/potions/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <climits>
using namespace std;

class Solution {
public:
    int minSmoke(vector<int>& A) {
        int n = A.size();
        vector<vector<int>> dp(n, vector<int>(n, 0));
        vector<vector<int>> color(n, vector<int>(n, 0));

        // Initialize color[i][i]
        for (int i = 0; i < n; ++i)
            color[i][i] = A[i];

        // l is the chain length
        for (int l = 2; l <= n; ++l) {
            for (int i = 0; i <= n - l; ++i) {
                int j = i + l - 1;
                dp[i][j] = INT_MAX;
                for (int k = i; k < j; ++k) {
                    int cost = dp[i][k] + dp[k+1][j] + color[i][k] * color[k+1][j];
                    if (cost < dp[i][j]) {
                        dp[i][j] = cost;
                        color[i][j] = (color[i][k] + color[k+1][j]) % 100;
                    }
                }
            }
        }

        return dp[0][n-1];
    }
};

```

## Code (Java)

```java
public class Solution {
    public int minSmoke(int[] A) {
        int n = A.length;
        int[][] dp = new int[n][n];
        int[][] color = new int[n][n];

        // Initialize color[i][i]
        for (int i = 0; i < n; i++)
            color[i][i] = A[i];

        // l is the chain length
        for (int l = 2; l <= n; l++) {
            for (int i = 0; i <= n - l; i++) {
                int j = i + l - 1;
                dp[i][j] = Integer.MAX_VALUE;
                for (int k = i; k < j; k++) {
                    int cost = dp[i][k] + dp[k+1][j] + color[i][k] * color[k+1][j];
                    if (cost < dp[i][j]) {
                        dp[i][j] = cost;
                        color[i][j] = (color[i][k] + color[k+1][j]) % 100;
                    }
                }
            }

```

## Code (Python)

```python
class Solution:
    # @param A : list of integers
    # @return an integer
    def minSmoke(self, A):
        n = len(A)
        dp = [[0]*n for _ in range(n)]
        color = [[0]*n for _ in range(n)]

        # Initialize color[i][i]
        for i in range(n):
            color[i][i] = A[i]

        # l is the chain length
        for l in range(2, n+1):
            for i in range(n-l+1):
                j = i + l - 1
                dp[i][j] = float('inf')
                for k in range(i, j):
                    cost = dp[i][k] + dp[k+1][j] + color[i][k]*color[k+1][j]
                    if cost < dp[i][j]:
                        dp[i][j] = cost
                        color[i][j] = (color[i][k] + color[k+1][j]) % 100

        return dp[0][n-1]

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
