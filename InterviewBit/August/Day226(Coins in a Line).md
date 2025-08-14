--- ❤️ ---

# 🚀 _Day 226. Coins in a Line_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/coins-in-a-line/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <algorithm>

using namespace std;

class Solution {
public:
    int maxcoin(vector<int>& A) {
        int n = A.size();
        vector<vector<int>> dp(n, vector<int>(n, 0));
        
        for (int i = n - 1; i >= 0; --i) {
            for (int j = i; j < n; ++j) {
                if (i == j) {
                    dp[i][j] = A[i];
                } else if (j == i + 1) {
                    dp[i][j] = max(A[i], A[j]);
                } else {
                    int option1 = A[i] + min(dp[i+2][j], dp[i+1][j-1]);
                    int option2 = A[j] + min(dp[i+1][j-1], dp[i][j-2]);
                    dp[i][j] = max(option1, option2);
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
    public int maxcoin(int[] A) {
        int n = A.length;
        int[][] dp = new int[n][n];
        
        for (int i = n - 1; i >= 0; i--) {
            for (int j = i; j < n; j++) {
                if (i == j) {
                    dp[i][j] = A[i];
                } else if (j == i + 1) {
                    dp[i][j] = Math.max(A[i], A[j]);
                } else {
                    int option1 = A[i] + Math.min(dp[i+2][j], dp[i+1][j-1]);
                    int option2 = A[j] + Math.min(dp[i+1][j-1], dp[i][j-2]);
                    dp[i][j] = Math.max(option1, option2);
                }
            }
        }
        
        return dp[0][n-1];
    }
}
```

## Code (Python)

```python
class Solution:
    def maxcoin(self, A):
        n = len(A)
        dp = [[0] * n for _ in range(n)]
        
        for i in range(n-1, -1, -1):
            for j in range(i, n):
                if i == j:
                    dp[i][j] = A[i]
                elif j == i + 1:
                    dp[i][j] = max(A[i], A[j])
                else:
                    option1 = A[i] + min(dp[i+2][j], dp[i+1][j-1])
                    option2 = A[j] + min(dp[i+1][j-1], dp[i][j-2])
                    dp[i][j] = max(option1, option2)
        
        return dp[0][n-1]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
