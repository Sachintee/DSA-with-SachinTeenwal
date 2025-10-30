---
title: "🔄 Replace O's with X's | GFG Solution 🎯"
keywords🏷️: ["🔄 surrounded regions", "🌊 DFS", "📍 BFS", "🔗 graph traversal", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Replace O's with X's problem: replace all 'O' surrounded by 'X' using boundary traversal and DFS/BFS techniques. 🚀"
date: 📅 2025-10-30
---

# *303. Replace O's with X's*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/replace-os-with-xs0052/1)

## **🧩 Problem Description**

You are given a grid[][] of size n*m, where every element is either 'O' or 'X'. Your task is to replace all 'O' or a group of 'O' with 'X' that are surrounded by 'X'.

A 'O' (or a set of 'O') is considered to be surrounded by 'X' if there are 'X' at locations just below, just above, just left and just right of it.


## Code(C++)
```cpp
class Solution {
public:
    void fill(vector<vector<char>>& g) {
        int m = g.size(), n = g[0].size();
        for (int i = 0; i < m; i++) for (int j = 0; j < n; j++) if (g[i][j] == 'O') g[i][j] = '-';
        function<void(int, int)> dfs = [&](int i, int j) {
            if (i < 0 || i >= m || j < 0 || j >= n || g[i][j] != '-') return;
            g[i][j] = 'O';
            dfs(i + 1, j); dfs(i - 1, j); dfs(i, j + 1); dfs(i, j - 1);
        };
        for (int i = 0; i < m; i++) { dfs(i, 0); dfs(i, n - 1); }
        for (int j = 0; j < n; j++) { dfs(0, j); dfs(m - 1, j); }
        for (int i = 0; i < m; i++) for (int j = 0; j < n; j++) if (g[i][j] == '-') g[i][j] = 'X';
    }
};
```

## Code (Java)

```java
class Solution {
    public void fill(char[][] g) {
        int m = g.length, n = g[0].length;
        for (int i = 0; i < m; i++) for (int j = 0; j < n; j++) if (g[i][j] == 'O') g[i][j] = '-';
        for (int i = 0; i < m; i++) { dfs(g, i, 0, m, n); dfs(g, i, n - 1, m, n); }
        for (int j = 0; j < n; j++) { dfs(g, 0, j, m, n); dfs(g, m - 1, j, m, n); }
        for (int i = 0; i < m; i++) for (int j = 0; j < n; j++) if (g[i][j] == '-') g[i][j] = 'X';
    }
    void dfs(char[][] g, int i, int j, int m, int n) {
        if (i < 0 || i >= m || j < 0 || j >= n || g[i][j] != '-') return;
        g[i][j] = 'O';
        dfs(g, i + 1, j, m, n); dfs(g, i - 1, j, m, n); dfs(g, i, j + 1, m, n); dfs(g, i, j - 1, m, n);
    }
}
```

## Code (Python)

```python
class Solution:
    def fill(self, g):
        m, n = len(g), len(g[0])
        for i in range(m):
            for j in range(n):
                if g[i][j] == 'O': g[i][j] = '-'
        def dfs(i, j):
            if i < 0 or i >= m or j < 0 or j >= n or g[i][j] != '-': return
            g[i][j] = 'O'
            dfs(i + 1, j); dfs(i - 1, j); dfs(i, j + 1); dfs(i, j - 1)
        for i in range(m): dfs(i, 0); dfs(i, n - 1)
        for j in range(n): dfs(0, j); dfs(m - 1, j)
        for i in range(m):
            for j in range(n):
                if g[i][j] == '-': g[i][j] = 'X'
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
