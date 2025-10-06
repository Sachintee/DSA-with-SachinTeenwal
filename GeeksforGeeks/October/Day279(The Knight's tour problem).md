---
title: "♞ Knight's Tour Problem | GFG Solution 🎯"
keywords🏷️: ["♞ knight tour", "🔄 backtracking", "♟️ chess problem", "🎯 recursion", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Knight's Tour Problem: find a sequence where a knight visits every square on an n×n chessboard exactly once using backtracking. 🚀"
date: 📅 2025-10-06
---

# *279. Knight's Tour Problem*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/the-knights-tour-problem/1)

## **🧩 Problem Description**

You are given an integer `n`, representing an `n × n` chessboard with a Knight starting at the top-left corner `(0, 0)`. Your task is to determine a valid **Knight's Tour**, where the Knight visits every square exactly once, following the standard movement rules of a chess Knight.

A Knight moves in an L-shape: two steps in one direction (horizontal or vertical) and one step perpendicular to that direction. For example, if a Knight is at cell `(2, 2)`, it can move to any of these cells: `(4, 3)`, `(4, 1)`, `(0, 3)`, `(0, 1)`, `(3, 4)`, `(3, 0)`, `(1, 4)`, and `(1, 0)`.

Return the order in which each cell is visited (starting from 0). If a solution exists, return the sequence of numbers representing the order of visited squares. If no solution is possible, return an empty list.


## Code(C++)
```cpp
class Solution {
public:
    vector<vector<int>> knightTour(int n) {
        vector<vector<int>> b(n, vector<int>(n, -1));
        int dx[] = {2, 1, -1, -2, -2, -1, 1, 2}, dy[] = {1, 2, 2, 1, -1, -2, -2, -1};
        function<bool(int, int, int)> solve = [&](int x, int y, int s) {
            if (s == n * n) return true;
            for (int i = 0; i < 8; i++) {
                int nx = x + dx[i], ny = y + dy[i];
                if (nx >= 0 && ny >= 0 && nx < n && ny < n && b[nx][ny] == -1) {
                    b[nx][ny] = s;
                    if (solve(nx, ny, s + 1)) return true;
                    b[nx][ny] = -1;
                }
            }
            return false;
        };
        b[0][0] = 0;
        return solve(0, 0, 1) ? b : vector<vector<int>>();
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<ArrayList<Integer>> knightTour(int n) {
        int[][] b = new int[n][n];
        for (int[] r : b) Arrays.fill(r, -1);
        int[] dx = {2, 1, -1, -2, -2, -1, 1, 2}, dy = {1, 2, 2, 1, -1, -2, -2, -1};
        b[0][0] = 0;
        if (solve(0, 0, 1, n, b, dx, dy)) {
            ArrayList<ArrayList<Integer>> res = new ArrayList<>();
            for (int[] r : b) {
                ArrayList<Integer> row = new ArrayList<>();
                for (int v : r) row.add(v);
                res.add(row);
            }
            return res;
        }
        return new ArrayList<>();
    }
    boolean solve(int x, int y, int s, int n, int[][] b, int[] dx, int[] dy) {
        if (s == n * n) return true;
        for (int i = 0; i < 8; i++) {
            int nx = x + dx[i], ny = y + dy[i];
            if (nx >= 0 && ny >= 0 && nx < n && ny < n && b[nx][ny] == -1) {
                b[nx][ny] = s;
                if (solve(nx, ny, s + 1, n, b, dx, dy)) return true;
                b[nx][ny] = -1;
            }
        }
        return false;
    }
}
```

## Code (Python)

```python
class Solution:
    def knightTour(self, n):
        b = [[-1] * n for _ in range(n)]
        dx, dy = [2, 1, -1, -2, -2, -1, 1, 2], [1, 2, 2, 1, -1, -2, -2, -1]
        def solve(x, y, s):
            if s == n * n: return True
            for i in range(8):
                nx, ny = x + dx[i], y + dy[i]
                if 0 <= nx < n and 0 <= ny < n and b[nx][ny] == -1:
                    b[nx][ny] = s
                    if solve(nx, ny, s + 1): return True
                    b[nx][ny] = -1
            return False
        b[0][0] = 0
        return b if solve(0, 0, 1) else []
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
