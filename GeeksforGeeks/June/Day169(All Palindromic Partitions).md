---
title: "🎯 All Palindromic Partitions | GFG Solution 🔍"
keywords🏷️: ["🎯 palindrome partitions", "🔍 dynamic programming", "📍 backtracking", "📈 string processing", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to All Palindromic Partitions problem: find all ways to partition string into palindromic substrings using DP preprocessing and backtracking. 🚀"
date: 📅 2025-06-18
---

# *169. All Palindromic Partitions*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/find-all-possible-palindromic-partitions-of-a-string/1)

## **🧩 Problem Description**

Given a string `s`, find all possible ways to partition it such that **every substring** in the partition is a **palindrome**.

A palindrome is a string that reads the same forward and backward.


## Code(C++)
```cpp
class Solution {
public:
    vector<vector<string>> palinParts(string& s) {
        int n = s.size();
        vector<vector<bool>> d(n, vector<bool>(n));
        for (int i = 0; i < n; i++) d[i][i] = true;
        for (int i = 0; i < n - 1; i++) d[i][i + 1] = s[i] == s[i + 1];
        for (int l = 3; l <= n; l++)
            for (int i = 0; i <= n - l; i++) {
                int j = i + l - 1;
                d[i][j] = s[i] == s[j] && d[i + 1][j - 1];
            }
        vector<vector<string>> r;
        vector<string> c;
        function<void(int)> b = [&](int i) {
            if (i == n) { r.push_back(c); return; }
            for (int j = i; j < n; j++)
                if (d[i][j]) {
                    c.push_back(s.substr(i, j - i + 1));
                    b(j + 1);
                    c.pop_back();
                }
        };
        b(0);
        return r;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<ArrayList<String>> palinParts(String s) {
        int n = s.length();
        boolean[][] d = new boolean[n][n];
        for (int i = 0; i < n; i++) d[i][i] = true;
        for (int i = 0; i < n - 1; i++) d[i][i + 1] = s.charAt(i) == s.charAt(i + 1);
        for (int l = 3; l <= n; l++)
            for (int i = 0; i <= n - l; i++) {
                int j = i + l - 1;
                d[i][j] = s.charAt(i) == s.charAt(j) && d[i + 1][j - 1];
            }
        ArrayList<ArrayList<String>> r = new ArrayList<>();
        ArrayList<String> c = new ArrayList<>();
        dfs(0, s, d, c, r);
        return r;
    }

    void dfs(int i, String s, boolean[][] d, ArrayList<String> c, ArrayList<ArrayList<String>> r) {
        if (i == s.length()) { r.add(new ArrayList<>(c)); return; }
        for (int j = i; j < s.length(); j++)
            if (d[i][j]) {
                c.add(s.substring(i, j + 1));
                dfs(j + 1, s, d, c, r);
                c.remove(c.size() - 1);
            }
    }
}
```

## Code (Python)

```python
class Solution:
    def palinParts(self, s):
        n = len(s)
        d = [[False]*n for _ in range(n)]
        for i in range(n): d[i][i] = True
        for i in range(n-1): d[i][i+1] = s[i] == s[i+1]
        for l in range(3, n+1):
            for i in range(n-l+1):
                j = i + l - 1
                d[i][j] = s[i] == s[j] and d[i+1][j-1]
        r = []
        def b(i, c):
            if i == n: r.append(c[:]); return
            for j in range(i, n):
                if d[i][j]:
                    c.append(s[i:j+1])
                    b(j+1, c)
                    c.pop()
        b(0, [])
        return r
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
