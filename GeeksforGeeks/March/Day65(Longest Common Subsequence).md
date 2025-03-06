---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Dynamic Programming
---

# 🚀 _Day 65. Longest Common Subsequence_ 🧠

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/dynamic-programming-gfg-160/problem/longest-common-subsequence-1587115620)

## 💡 **Problem Description:**

Given **two strings** `s1` and `s2`, **return the length of their longest common subsequence (LCS)**. If there is no common subsequence, return `0`.  


## Code(C++)
```cpp
class Solution {
public:
    int lcs(string &s1, string &s2) {
        int n = s1.size(), m = s2.size();
        vector<int> prev(m + 1, 0), curr(m + 1, 0);
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= m; j++) {
                curr[j] = s1[i - 1] == s2[j - 1] ? prev[j - 1] + 1 : max(prev[j], curr[j - 1]);
            }
            swap(prev, curr);
        }
        return prev[m];
    }
};
```

## Code (Java)

```java
class Solution {
    static int lcs(String s1, String s2) {
        int n = s1.length(), m = s2.length();
        int[] prev = new int[m + 1], curr = new int[m + 1];
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= m; j++) {
                curr[j] = s1.charAt(i - 1) == s2.charAt(j - 1) ? prev[j - 1] + 1 : Math.max(prev[j], curr[j - 1]);
            }
            int[] temp = prev; prev = curr; curr = temp;
        }
        return prev[m];
    }
}
```

## Code (Python)

```python
class Solution:
    def lcs(self, s1, s2):
        m, n = len(s1), len(s2)
        dp = [0] * (n + 1)
        for i in range(m):
            prev = 0
            for j in range(n):
                temp = dp[j + 1]
                dp[j + 1] = prev + 1 if s1[i] == s2[j] else max(dp[j + 1], dp[j])
                prev = temp
        return dp[n]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
