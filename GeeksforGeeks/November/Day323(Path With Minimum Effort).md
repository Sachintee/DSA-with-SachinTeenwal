---
title: "🗺️ Path With Minimum Effort | GFG Solution 🔍"
keywords🏷️: ["🗺️ path finding", "🔍 dijkstra", "📍 graph traversal", "📈 priority queue", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Path With Minimum Effort problem: find minimum cost path where cost is maximum absolute difference between consecutive cells using Dijkstra's algorithm. 🚀"
date: 📅 2025-11-19
---

# *323. Path With Minimum Effort*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/path-with-minimum-effort/1)

## **🧩 Problem Description**

You are given a 2D array `mat[][]` of size `n*m`. Your task is to find the **minimum possible path cost** from the top-left cell (0, 0) to the bottom-right cell (n-1, m-1) by moving up, down, left, or right between adjacent cells.

**Note:** The cost of a path is defined as the **maximum absolute difference** between the values of any two consecutive cells along that path.


## Code(C++)
```cpp
class Solution {
public:
    int minCostPath(vector<vector<int>> &mat) {
        int n = mat.size(), m = mat[0].size();
        vector<vector<int>> dist(n, vector<int>(m, 1e9));
        priority_queue<tuple<int,int,int>, vector<tuple<int,int,int>>, greater<>> pq;
        pq.push({0, 0, 0});
        dist[0][0] = 0;
        int dx[] = {-1, 1, 0, 0}, dy[] = {0, 0, -1, 1};
        while (!pq.empty()) {
            auto [d, x, y] = pq.top(); pq.pop();
            if (x == n - 1 && y == m - 1) return d;
            if (d > dist[x][y]) continue;
            for (int i = 0; i < 4; i++) {
                int nx = x + dx[i], ny = y + dy[i];
                if (nx >= 0 && nx < n && ny >= 0 && ny < m) {
                    int nd = max(d, abs(mat[nx][ny] - mat[x][y]));
                    if (nd < dist[nx][ny]) {
                        dist[nx][ny] = nd;
                        pq.push({nd, nx, ny});
                    }
                }
            }
        }
        return dist[n - 1][m - 1];
    }
};
```

## Code (Java)

```java
class Solution {
    public int minCostPath(int[][] mat) {
        int n = mat.length, m = mat[0].length;
        int[][] dist = new int[n][m];
        for (int[] row : dist) Arrays.fill(row, Integer.MAX_VALUE);
        PriorityQueue<int[]> pq = new PriorityQueue<>((a, b) -> a[0] - b[0]);
        pq.offer(new int[]{0, 0, 0});
        dist[0][0] = 0;
        int[] dx = {-1, 1, 0, 0}, dy = {0, 0, -1, 1};
        while (!pq.isEmpty()) {
            int[] curr = pq.poll();
            int d = curr[0], x = curr[1], y = curr[2];
            if (x == n - 1 && y == m - 1) return d;
            if (d > dist[x][y]) continue;
            for (int i = 0; i < 4; i++) {
                int nx = x + dx[i], ny = y + dy[i];
                if (nx >= 0 && nx < n && ny >= 0 && ny < m) {
                    int nd = Math.max(d, Math.abs(mat[nx][ny] - mat[x][y]));
                    if (nd < dist[nx][ny]) {
                        dist[nx][ny] = nd;
                        pq.offer(new int[]{nd, nx, ny});
                    }
                }
            }
        }
        return dist[n - 1][m - 1];
    }
}
```

## Code (Python)

```python
from heapq import heappush, heappop

class Solution:
    def minCostPath(self, mat):
        n, m = len(mat), len(mat[0])
        dist = [[float('inf')] * m for _ in range(n)]
        pq = [(0, 0, 0)]
        dist[0][0] = 0
        dx, dy = [-1, 1, 0, 0], [0, 0, -1, 1]
        while pq:
            d, x, y = heappop(pq)
            if x == n - 1 and y == m - 1: return d
            if d > dist[x][y]: continue
            for i in range(4):
                nx, ny = x + dx[i], y + dy[i]
                if 0 <= nx < n and 0 <= ny < m:
                    nd = max(d, abs(mat[nx][ny] - mat[x][y]))
                    if nd < dist[nx][ny]:
                        dist[nx][ny] = nd
                        heappush(pq, (nd, nx, ny))
        return dist[n - 1][m - 1]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
