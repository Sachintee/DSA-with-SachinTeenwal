--- ❤️ ---

# 🚀 _Day 208. Longest Palindromic Subsequence_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/longest-palindromic-subsequence/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <vector>
#include <string>
using namespace std;

class Solution {
public:
    int solve(string A) {
        int n = A.size();
        vector<vector<int>> dp(n, vector<int>(n, 0));

        for (int i = 0; i < n; ++i)
            dp[i][i] = 1;

        for (int length = 2; length <= n; ++length) {
            for (int i = 0; i <= n - length; ++i) {
                int j = i + length - 1;
                if (A[i] == A[j]) {
                    dp[i][j] = (length == 2) ? 2 : 2 + dp[i + 1][j - 1];
                } else {
                    dp[i][j] = max(dp[i + 1][j], dp[i][j - 1]);
                }
            }
        }
        return dp[0][n - 1];
    }
};

// Example usage
int main() {
    Solution sol;
    string A = "bebeeed";
    cout << sol.solve(A) << endl;  // Output: 4
    return 0;
}

```

## Code (Java)

```java
public class Solution {
    public int solve(String A) {
        int n = A.length();
        int[][] dp = new int[n][n];

        for (int i = 0; i < n; i++)
            dp[i][i] = 1;

        for (int length = 2; length <= n; length++) {
            for (int i = 0; i <= n - length; i++) {
                int j = i + length - 1;
                if (A.charAt(i) == A.charAt(j)) {
                    dp[i][j] = (length == 2) ? 2 : 2 + dp[i + 1][j - 1];
                } else {
                    dp[i][j] = Math.max(dp[i + 1][j], dp[i][j - 1]);
                }
            }
        }
        return dp[0][n - 1];
    }

    // Example usage
    public static void main(String[] args) {
        Solution sol = new Solution();
        String A = "bebeeed";
        System.out.println(sol.solve(A));  // Output: 4
    }
}

```

## Code (Python)

```python
class Solution:
    # @param A : string
    # @return an integer
    def solve(self, A):
        n = len(A)
        dp = [[0] * n for _ in range(n)]

        # Every single character is a palindrome of length 1
        for i in range(n):
            dp[i][i] = 1

        # Build the DP table
        for length in range(2, n + 1):  # length of substring
            for i in range(n - length + 1):
                j = i + length - 1
                if A[i] == A[j]:
                    if length == 2:
                        dp[i][j] = 2
                    else:
                        dp[i][j] = 2 + dp[i + 1][j - 1]
                else:
                    dp[i][j] = max(dp[i + 1][j], dp[i][j - 1])

        return dp[0][n - 1]

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
