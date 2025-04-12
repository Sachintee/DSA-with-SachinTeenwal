---
Difficulty: Medium
Source: 160 Days of Problem Solving
Tags:
  - Graph
  - Recursion
  - DFS
  - Matrix
---

# 🚀 _Day 102. Flood fill Algorithm_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/graph-gfg-160/problem/flood-fill-algorithm1856)

## 💡 **Problem Description:**

You are given a 2D grid `image[][]` of size n×m, where each `image[i][j]` represents the color of a pixel in the image. You are also provided with a coordinate `(sr, sc)` representing the starting pixel (row and column) and a new color value `newColor`.  

Your task is to perform a **flood fill** starting from the pixel `(sr, sc)`, changing its color to `newColor` and also changing the color of all connected pixels that have the same original color. Two pixels are considered connected if they are adjacent horizontally or vertically (not diagonally) and share the same original color.


## Code(C++)
```cpp
class Solution {
  public:
    vector<vector<int>> floodFill(vector<vector<int>>& A, int sr, int sc, int nc) {
        int m = A.size(), n = A[0].size(), oc = A[sr][sc];
        if (oc == nc) return A;
        queue<pair<int, int>> q; q.push({sr, sc});
        A[sr][sc] = nc;
        int d[5] = {-1, 0, 1, 0, -1};
        while (!q.empty()) {
            int x = q.front().first, y = q.front().second; q.pop();
            for (int i = 0; i < 4; i++) {
                int nx = x + d[i], ny = y + d[i+1];
                if (nx >= 0 && ny >= 0 && nx < m && ny < n && A[nx][ny] == oc) {
                    A[nx][ny] = nc;
                    q.push({nx, ny});
                }
            }
        }
        return A;
    }
};
```

## Code (Java)

```java
class Solution {
    public int[][] floodFill(int[][] A, int sr, int sc, int nc) {
        int m = A.length, n = A[0].length, oc = A[sr][sc];
        if (oc == nc) return A;
        Queue<int[]> q = new LinkedList<>();
        q.add(new int[]{sr, sc});
        A[sr][sc] = nc;
        int[] d = {-1, 0, 1, 0, -1};
        while (!q.isEmpty()) {
            int[] p = q.poll();
            for (int i = 0; i < 4; i++) {
                int x = p[0] + d[i], y = p[1] + d[i+1];
                if (x >= 0 && y >= 0 && x < m && y < n && A[x][y] == oc) {
                    A[x][y] = nc;
                    q.add(new int[]{x, y});
                }
            }
        }
        return A;
    }
}
```

## Code (Python)

```python
class Solution:
    def floodFill(self, A, sr, sc, nc):
        m, n, oc = len(A), len(A[0]), A[sr][sc]
        if oc == nc: return A
        q = [(sr, sc)]
        A[sr][sc] = nc
        d = [-1, 0, 1, 0, -1]
        while q:
            x, y = q.pop(0)
            for i in range(4):
                nx, ny = x + d[i], y + d[i+1]
                if 0 <= nx < m and 0 <= ny < n and A[nx][ny] == oc:
                    A[nx][ny] = nc
                    q.append((nx, ny))
        return A
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
