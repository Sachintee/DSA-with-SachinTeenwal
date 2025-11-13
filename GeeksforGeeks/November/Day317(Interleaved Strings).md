---
title: "🔀 Interleaved Strings | GFG Solution 🔍"
keywords🏷️: ["🔀 interleaved strings", "🔍 dynamic programming", "📍 string matching", "📈 memoization", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Interleaved Strings problem: determine if string s3 is formed by interleaving s1 and s2 while maintaining character order using dynamic programming. 🚀"
date: 📅 2025-11-13
---

# *317. Interleaved Strings*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/interleaved-strings/1)

## **🧩 Problem Description**

Given strings `s1`, `s2`, and `s3`, find whether `s3` is formed by an **interleaving** of `s1` and `s2`.


## Code(C++)
```cpp
class Solution {
public:
    bool isInterleave(string &s1, string &s2, string &s3) {
        if (s1.size() + s2.size() != s3.size()) return false;
        int n = s1.size(), m = s2.size();
        vector<bool> dp(m + 1);
        dp[0] = true;
        for (int j = 1; j <= m; j++) dp[j] = dp[j - 1] && s2[j - 1] == s3[j - 1];
        for (int i = 1; i <= n; i++) {
            dp[0] = dp[0] && s1[i - 1] == s3[i - 1];
            for (int j = 1; j <= m; j++)
                dp[j] = (dp[j] && s1[i - 1] == s3[i + j - 1]) || (dp[j - 1] && s2[j - 1] == s3[i + j - 1]);
        }
        return dp[m];
    }
};
```

## Code (Java)

```java
class Solution {
    public boolean isInterleave(String s1, String s2, String s3) {
        if (s1.length() + s2.length() != s3.length()) return false;
        int n = s1.length(), m = s2.length();
        boolean[] dp = new boolean[m + 1];
        dp[0] = true;
        for (int j = 1; j <= m; j++) dp[j] = dp[j - 1] && s2.charAt(j - 1) == s3.charAt(j - 1);
        for (int i = 1; i <= n; i++) {
            dp[0] = dp[0] && s1.charAt(i - 1) == s3.charAt(i - 1);
            for (int j = 1; j <= m; j++)
                dp[j] = (dp[j] && s1.charAt(i - 1) == s3.charAt(i + j - 1)) || (dp[j - 1] && s2.charAt(j - 1) == s3.charAt(i + j - 1));
        }
        return dp[m];
    }
}
```

## Code (Python)

```python
class Solution:
    def isInterleave(self, s1, s2, s3):
        if len(s1) + len(s2) != len(s3): return False
        n, m = len(s1), len(s2)
        dp = [False] * (m + 1)
        dp[0] = True
        for j in range(1, m + 1): dp[j] = dp[j - 1] and s2[j - 1] == s3[j - 1]
        for i in range(1, n + 1):
            dp[0] = dp[0] and s1[i - 1] == s3[i - 1]
            for j in range(1, m + 1):
                dp[j] = (dp[j] and s1[i - 1] == s3[i + j - 1]) or (dp[j - 1] and s2[j - 1] == s3[i + j - 1])
        return dp[m]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
