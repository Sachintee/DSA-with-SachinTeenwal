---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Dynamic Programming
  - Strings
  - palindrome
---

# 🚀 _Day 68. Palindrome SubStrings_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/count-palindrome-sub-strings-of-a-string0652/1)

## 💡 **Problem Description:**

Given a string **s**, count all **palindromic substrings** present in the string where the **length of each palindromic substring** is **greater than or equal to 2**.


## Code(C++)
```cpp
class Solution {
  public:
    int countPS(string& s) {
        int n = s.size(), res = 0;
        vector<vector<bool>> dp(n, vector<bool>(n));
        for (int i = n - 1; i >= 0; --i) {
            dp[i][i] = true;
            for (int j = i + 1; j < n; ++j)
                if (s[i] == s[j] && (j - i == 1 || dp[i + 1][j - 1]))
                    dp[i][j] = true, res++;
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public int countPS(String s) {
        int n = s.length(), res = 0;
        boolean[][] dp = new boolean[n][n];
        for (int i = n - 1; i >= 0; i--) {
            dp[i][i] = true;
            for (int j = i + 1; j < n; j++)
                if (s.charAt(i) == s.charAt(j) && (j - i == 1 || dp[i + 1][j - 1])) {
                    dp[i][j] = true;
                    res++;
                }
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def countPS(self, s):
        n, res = len(s), 0
        dp = [[False] * n for _ in range(n)]
        for i in range(n - 1, -1, -1):
            dp[i][i] = True
            for j in range(i + 1, n):
                if s[i] == s[j] and (j - i == 1 or dp[i + 1][j - 1]):
                    dp[i][j] = True
                    res += 1
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
