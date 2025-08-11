--- ❤️ ---

# 🚀 _Day 223. Min Sum Path in Matrix_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/min-sum-path-in-matrix/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <algorithm>

using namespace std;

class Solution {
public:
    int minPathSum(vector<vector<int>>& A) {
        if (A.empty() || A[0].empty()) return 0;
        
        int m = A.size();
        int n = A[0].size();
        
        vector<vector<int>> dp(m, vector<int>(n, 0));
        
        dp[0][0] = A[0][0];
        
        for (int j = 1; j < n; ++j) {
            dp[0][j] = dp[0][j-1] + A[0][j];
        }
        
        for (int i = 1; i < m; ++i) {
            dp[i][0] = dp[i-1][0] + A[i][0];
        }
        
        for (int i = 1; i < m; ++i) {
            for (int j = 1; j < n; ++j) {
                dp[i][j] = min(dp[i-1][j], dp[i][j-1]) + A[i][j];
            }
        }
        
        return dp[m-1][n-1];
    }
};
```

## Code (Java)

```java
public class Solution {
    public int minPathSum(int[][] A) {
        if (A == null || A.length == 0 || A[0].length == 0) return 0;
        
        int m = A.length;
        int n = A[0].length;
        
        int[][] dp = new int[m][n];
        
        dp[0][0] = A[0][0];
        
        for (int j = 1; j < n; j++) {
            dp[0][j] = dp[0][j-1] + A[0][j];
        }
        
        for (int i = 1; i < m; i++) {
            dp[i][0] = dp[i-1][0] + A[i][0];
        }
        
        for (int i = 1; i < m; i++) {
            for (int j = 1; j < n; j++) {
                dp[i][j] = Math.min(dp[i-1][j], dp[i][j-1]) + A[i][j];
            }
        }
        
        return dp[m-1][n-1];
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : list of list of integers
    # @return an integer
    def minPathSum(self, A):
        if not A or not A[0]:
            return 0
        
        m = len(A)
        n = len(A[0])
        
        # Create a DP table initialized to 0
        dp = [[0 for _ in range(n)] for _ in range(m)]
        
        # Initialize the starting point
        dp[0][0] = A[0][0]
        
        # Fill the first row
        for j in range(1, n):
            dp[0][j] = dp[0][j-1] + A[0][j]
        
        # Fill the first column
        for i in range(1, m):
            dp[i][0] = dp[i-1][0] + A[i][0]
        
        # Fill the rest of the table
        for i in range(1, m):
            for j in range(1, n):
                dp[i][j] = min(dp[i-1][j], dp[i][j-1]) + A[i][j]
        
        return dp[m-1][n-1]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
