--- ❤️ ---

# 🚀 _Day 220. Palindrome Partitioning II_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/palindrome-partitioning-ii/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int minCut(string A) {
        int n = A.size();
        vector<vector<bool>> isPalindrome(n, vector<bool>(n, false));
        vector<int> dp(n, 0);

        // Fill palindrome table
        for (int i = 0; i < n; i++) {
            isPalindrome[i][i] = true;
        }

        for (int len = 2; len <= n; len++) {
            for (int i = 0; i <= n - len; i++) {
                int j = i + len - 1;
                if (A[i] == A[j]) {
                    if (len == 2) {
                        isPalindrome[i][j] = true;
                    } else {
                        isPalindrome[i][j] = isPalindrome[i + 1][j - 1];
                    }
                }
            }
        }

        // Fill dp array
        for (int i = 0; i < n; i++) {
            if (isPalindrome[0][i]) {
                dp[i] = 0;
            } else {
                int minCut = INT_MAX;
                for (int j = 1; j <= i; j++) {
                    if (isPalindrome[j][i]) {
                        minCut = min(minCut, dp[j - 1] + 1);
                    }
                }
                dp[i] = minCut;
            }
        }

        return dp[n - 1];
    }
};

```

## Code (Java)

```java
public class Solution {
    public int minCut(String A) {
        int n = A.length();
        boolean[][] isPalindrome = new boolean[n][n];
        int[] dp = new int[n];

        // Fill palindrome table
        for (int i = 0; i < n; i++) {
            isPalindrome[i][i] = true;
        }

        for (int len = 2; len <= n; len++) {
            for (int i = 0; i <= n - len; i++) {
                int j = i + len - 1;
                if (A.charAt(i) == A.charAt(j)) {
                    if (len == 2) {
                        isPalindrome[i][j] = true;
                    } else {
                        isPalindrome[i][j] = isPalindrome[i + 1][j - 1];
                    }
                }
            }
        }

        // Fill dp array
        for (int i = 0; i < n; i++) {
            if (isPalindrome[0][i]) {
                dp[i] = 0;
            } else {
                int minCut = Integer.MAX_VALUE;
                for (int j = 1; j <= i; j++) {
                    if (isPalindrome[j][i]) {
                        minCut = Math.min(minCut, dp[j - 1] + 1);
                    }
                }
                dp[i] = minCut;
            }
        }

        return dp[n - 1];
    }
}

```

## Code (Python)

```python
class Solution:
    def minCut(self, A):
        n = len(A)
        # Step 1: Build palindrome table
        is_palindrome = [[False]*n for _ in range(n)]
        
        for i in range(n):
            is_palindrome[i][i] = True
            
        for length in range(2, n+1):
            for i in range(n - length + 1):
                j = i + length - 1
                if A[i] == A[j]:
                    if length == 2:
                        is_palindrome[i][j] = True
                    else:
                        is_palindrome[i][j] = is_palindrome[i+1][j-1]
        
        # Step 2: DP to find min cuts
        dp = [0] * n
        for i in range(n):
            if is_palindrome[0][i]:
                dp[i] = 0
            else:
                min_cut = float('inf')
                for j in range(1, i+1):
                    if is_palindrome[j][i]:
                        min_cut = min(min_cut, dp[j-1] + 1)
                dp[i] = min_cut
        return dp[n-1]

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
