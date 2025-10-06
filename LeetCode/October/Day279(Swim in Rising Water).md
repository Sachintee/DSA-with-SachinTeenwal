--- ❤️ ---

# 🚀 _Day 279. Swim in Rising Water_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/swim-in-rising-water/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int swimInWater(vector<vector<int>>& grid) {
        int n = grid.size();
        int m = n * n;
        vector<int> p(m);
        iota(p.begin(), p.end(), 0);

        auto find = [&](this auto&& find, int x) -> int {
            if (p[x] != x) {
                p[x] = find(p[x]);
            }
            return p[x];
        };

        vector<int> hi(m);
        for (int i = 0; i < n; ++i) {
            for (int j = 0; j < n; ++j) {
                hi[grid[i][j]] = i * n + j;
            }
        }

        array<int, 5> dirs{-1, 0, 1, 0, -1};

        for (int t = 0; t < m; ++t) {
            int id = hi[t];
            int x = id / n, y = id % n;
            for (int k = 0; k < 4; ++k) {
                int nx = x + dirs[k], ny = y + dirs[k + 1];
                if (nx >= 0 && nx < n && ny >= 0 && ny < n && grid[nx][ny] <= t) {
                    int a = find(x * n + y);
                    int b = find(nx * n + ny);
                    p[a] = b;
                }
            }
            if (find(0) == find(m - 1)) {
                return t;
            }
        }
        return 0;
    }
};
```

## Code (Java)

```java
class Solution {
    public int swimInWater(int[][] grid) {
        int n = grid.length;
        int m = n * n;
        int[] p = new int[m];
        Arrays.setAll(p, i -> i);
        IntUnaryOperator find = new IntUnaryOperator() {
            @Override
            public int applyAsInt(int x) {
                if (p[x] != x) p[x] = applyAsInt(p[x]);
                return p[x];
            }
        };

        int[] hi = new int[m];
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                hi[grid[i][j]] = i * n + j;
            }
        }

        int[] dirs = {-1, 0, 1, 0, -1};

        for (int t = 0; t < m; t++) {
            int id = hi[t];
            int x = id / n, y = id % n;
            for (int k = 0; k < 4; k++) {
                int nx = x + dirs[k], ny = y + dirs[k + 1];
                if (nx >= 0 && nx < n && ny >= 0 && ny < n && grid[nx][ny] <= t) {
                    int a = find.applyAsInt(x * n + y);
                    int b = find.applyAsInt(nx * n + ny);
                    p[a] = b;
                }
            }
            if (find.applyAsInt(0) == find.applyAsInt(m - 1)) {
                return t;
            }
        }
        return 0;
    }
}
```

## Code (Python)

```python
class Solution:
    def swimInWater(self, grid: List[List[int]]) -> int:
        def find(x: int) -> int:
            if p[x] != x:
                p[x] = find(p[x])
            return p[x]

        n = len(grid)
        m = n * n
        p = list(range(m))
        hi = [0] * m
        for i, row in enumerate(grid):
            for j, h in enumerate(row):
                hi[h] = i * n + j
        dirs = (-1, 0, 1, 0, -1)
        for t in range(m):
            x, y = divmod(hi[t], n)
            for dx, dy in pairwise(dirs):
                nx, ny = x + dx, y + dy
                if 0 <= nx < n and 0 <= ny < n and grid[nx][ny] <= t:
                    p[find(x * n + y)] = find(nx * n + ny)
            if find(0) == find(m - 1):
                return t
        return 0
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
