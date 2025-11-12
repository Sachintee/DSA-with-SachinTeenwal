--
title: "🎭 Wildcard Pattern Matching | GFG Solution 🎯"
keywords🏷️: ["🎭 pattern matching", "🔍 dynamic programming", "📍 wildcard", "📈 string matching", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Wildcard Pattern Matching problem: determine if a pattern with wildcards ('?' and '*') matches a given text using dynamic programming. 🚀"
date: 📅 2025-11-12
---

# *316. Wildcard Pattern Matching*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/wildcard-pattern-matching/1)

## **🧩 Problem Description**

Given two strings `txt` and `pat` which may be of different sizes, you have to return `true` if the wildcard pattern `pat` matches with `txt`, else return `false`.

The wildcard pattern `pat` can include the characters `'?'` and `'*'`:
- `'?'` – matches any single character.
- `'*'` – matches any sequence of characters (including the empty sequence).


## Code(C++)
```cpp
class Solution {
public:
    bool wildCard(string &txt, string &pat) {
        int n = txt.size(), m = pat.size();
        vector<vector<bool>> dp(n + 1, vector<bool>(m + 1, false));
        dp[0][0] = true;
        for (int j = 1; j <= m; j++) 
            if (pat[j - 1] == '*') dp[0][j] = dp[0][j - 1];
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= m; j++) {
                if (pat[j - 1] == '*') 
                    dp[i][j] = dp[i][j - 1] || dp[i - 1][j];
                else if (pat[j - 1] == '?' || txt[i - 1] == pat[j - 1]) 
                    dp[i][j] = dp[i - 1][j - 1];
            }
        }
        return dp[n][m];
    }
};
```

## Code (Java)

```java
class Solution {
    public boolean wildCard(String txt, String pat) {
        int n = txt.length(), m = pat.length();
        boolean[][] dp = new boolean[n + 1][m + 1];
        dp[0][0] = true;
        for (int j = 1; j <= m; j++) 
            if (pat.charAt(j - 1) == '*') dp[0][j] = dp[0][j - 1];
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= m; j++) {
                if (pat.charAt(j - 1) == '*') 
                    dp[i][j] = dp[i][j - 1] || dp[i - 1][j];
                else if (pat.charAt(j - 1) == '?' || txt.charAt(i - 1) == pat.charAt(j - 1)) 
                    dp[i][j] = dp[i - 1][j - 1];
            }
        }
        return dp[n][m];
    }
}
```

## Code (Python)

```python
class Solution:
    def wildCard(self, txt, pat):
        n, m = len(txt), len(pat)
        dp = [[False] * (m + 1) for _ in range(n + 1)]
        dp[0][0] = True
        for j in range(1, m + 1):
            if pat[j - 1] == '*': dp[0][j] = dp[0][j - 1]
        for i in range(1, n + 1):
            for j in range(1, m + 1):
                if pat[j - 1] == '*':
                    dp[i][j] = dp[i][j - 1] or dp[i - 1][j]
                elif pat[j - 1] == '?' or txt[i - 1] == pat[j - 1]:
                    dp[i][j] = dp[i - 1][j - 1]
        return dp[n][m]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
