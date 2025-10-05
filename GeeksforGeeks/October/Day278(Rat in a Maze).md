---
title: "🐭 Rat in a Maze | GFG Solution 🔍"
keywords🏷️: ["🐭 rat in maze", "🔍 backtracking", "📍 DFS", "🔄 recursion", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Rat in a Maze problem: find all possible paths from source to destination using backtracking and DFS technique. 🚀"
date: 📅 2025-10-05
---

# *278. Rat in a Maze*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/rat-in-a-maze-problem/1)

## **🧩 Problem Description**

Consider a rat placed at position **(0, 0)** in an **n x n** square matrix `maze[][]`. The rat's goal is to reach the destination at position **(n-1, n-1)**. The rat can move in four possible directions: **'U'** (up), **'D'** (down), **'L'** (left), **'R'** (right).


## Code(C++)
```cpp
class Solution {
public:
    vector<string> ratInMaze(vector<vector<int>>& m) {
        vector<string> res;
        int n = m.size();
        if (!m[0][0] || !m[n-1][n-1]) return res;
        string p = "";
        solve(0, 0, m, n, p, res);
        return res;
    }
    
    void solve(int i, int j, vector<vector<int>>& m, int n, string p, vector<string>& res) {
        if (i == n-1 && j == n-1) {
            res.push_back(p);
            return;
        }
        m[i][j] = 0;
        if (i+1 < n && m[i+1][j]) solve(i+1, j, m, n, p+'D', res);
        if (j-1 >= 0 && m[i][j-1]) solve(i, j-1, m, n, p+'L', res);
        if (j+1 < n && m[i][j+1]) solve(i, j+1, m, n, p+'R', res);
        if (i-1 >= 0 && m[i-1][j]) solve(i-1, j, m, n, p+'U', res);
        m[i][j] = 1;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<String> ratInMaze(int[][] m) {
        ArrayList<String> res = new ArrayList<>();
        int n = m.length;
        if (m[0][0] == 0 || m[n-1][n-1] == 0) return res;
        solve(0, 0, m, n, "", res);
        return res;
    }
    
    void solve(int i, int j, int[][] m, int n, String p, ArrayList<String> res) {
        if (i == n-1 && j == n-1) {
            res.add(p);
            return;
        }
        m[i][j] = 0;
        if (i+1 < n && m[i+1][j] == 1) solve(i+1, j, m, n, p+'D', res);
        if (j-1 >= 0 && m[i][j-1] == 1) solve(i, j-1, m, n, p+'L', res);
        if (j+1 < n && m[i][j+1] == 1) solve(i, j+1, m, n, p+'R', res);
        if (i-1 >= 0 && m[i-1][j] == 1) solve(i-1, j, m, n, p+'U', res);
        m[i][j] = 1;
    }
}
```

## Code (Python)

```python
class Solution:
    def ratInMaze(self, m):
        res = []
        n = len(m)
        if not m[0][0] or not m[n-1][n-1]: return res
        self.solve(0, 0, m, n, "", res)
        return res
    
    def solve(self, i, j, m, n, p, res):
        if i == n-1 and j == n-1:
            res.append(p)
            return
        m[i][j] = 0
        if i+1 < n and m[i+1][j]: self.solve(i+1, j, m, n, p+'D', res)
        if j-1 >= 0 and m[i][j-1]: self.solve(i, j-1, m, n, p+'L', res)
        if j+1 < n and m[i][j+1]: self.solve(i, j+1, m, n, p+'R', res)
        if i-1 >= 0 and m[i-1][j]: self.solve(i-1, j, m, n, p+'U', res)
        m[i][j] = 1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
