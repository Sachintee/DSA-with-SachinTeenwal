

# 🚀 _Day 365. Last Day Where You Can Still Cross_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/last-day-where-you-can-still-cross/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int latestDayToCross(int row, int col, vector<vector<int>>& cells) {
        int l = 1, r = cells.size();
        int g[row][col];
        int dirs[5] = {0, 1, 0, -1, 0};
        auto check = [&](int k) -> bool {
            memset(g, 0, sizeof(g));
            for (int i = 0; i < k; ++i) {
                g[cells[i][0] - 1][cells[i][1] - 1] = 1;
            }
            queue<pair<int, int>> q;
            for (int j = 0; j < col; ++j) {
                if (g[0][j] == 0) {
                    q.emplace(0, j);
                    g[0][j] = 1;
                }
            }
            while (!q.empty()) {
                auto [x, y] = q.front();
                q.pop();
                if (x == row - 1) {
                    return true;
                }
                for (int i = 0; i < 4; ++i) {
                    int nx = x + dirs[i];
                    int ny = y + dirs[i + 1];
                    if (nx >= 0 && nx < row && ny >= 0 && ny < col && g[nx][ny] == 0) {
                        q.emplace(nx, ny);
                        g[nx][ny] = 1;
                    }
                }
            }
            return false;
        };
        while (l < r) {
            int mid = (l + r + 1) >> 1;
            if (check(mid)) {
                l = mid;
            } else {
                r = mid - 1;
            }
        }
        return l;
    }
};
```

## Code (Java)

```java
class Solution {
    private int[][] cells;
    private int m;
    private int n;

    public int latestDayToCross(int row, int col, int[][] cells) {
        int l = 1, r = cells.length;
        this.cells = cells;
        this.m = row;
        this.n = col;
        while (l < r) {
            int mid = (l + r + 1) >> 1;
            if (check(mid)) {
                l = mid;
            } else {
                r = mid - 1;
            }
        }
        return l;
    }

    private boolean check(int k) {
        int[][] g = new int[m][n];
        for (int i = 0; i < k; i++) {
            g[cells[i][0] - 1][cells[i][1] - 1] = 1;
        }
        final int[] dirs = {-1, 0, 1, 0, -1};
        Deque<int[]> q = new ArrayDeque<>();
        for (int j = 0; j < n; j++) {
            if (g[0][j] == 0) {
                q.offer(new int[] {0, j});
                g[0][j] = 1;
            }
        }
        while (!q.isEmpty()) {
            int[] p = q.poll();
            int x = p[0], y = p[1];
            if (x == m - 1) {
                return true;
            }
            for (int i = 0; i < 4; i++) {
                int nx = x + dirs[i], ny = y + dirs[i + 1];
                if (nx >= 0 && nx < m && ny >= 0 && ny < n && g[nx][ny] == 0) {
                    q.offer(new int[] {nx, ny});
                    g[nx][ny] = 1;
                }
            }
        }
        return false;
    }
}
```

## Code (Python3)

```python
class Solution:
    def latestDayToCross(self, row: int, col: int, cells: List[List[int]]) -> int:
        def check(k: int) -> bool:
            g = [[0] * col for _ in range(row)]
            for i, j in cells[:k]:
                g[i - 1][j - 1] = 1
            q = [(0, j) for j in range(col) if g[0][j] == 0]
            for x, y in q:
                if x == row - 1:
                    return True
                for a, b in pairwise(dirs):
                    nx, ny = x + a, y + b
                    if 0 <= nx < row and 0 <= ny < col and g[nx][ny] == 0:
                        q.append((nx, ny))
                        g[nx][ny] = 1
            return False

        n = row * col
        l, r = 1, n
        dirs = (-1, 0, 1, 0, -1)
        while l < r:
            mid = (l + r + 1) >> 1
            if check(mid):
                l = mid
            else:
                r = mid - 1
        return l
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
