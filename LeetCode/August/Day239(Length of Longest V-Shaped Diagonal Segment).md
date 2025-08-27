--- ❤️ ---

# 🚀 _Day 239. Length of Longest V-Shaped Diagonal Segment_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/length-of-longest-v-shaped-diagonal-segment/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    static constexpr int MAXN = 501;
    int f[MAXN][MAXN][4][2];

    int lenOfVDiagonal(vector<vector<int>>& grid) {
        int m = grid.size(), n = grid[0].size();
        int dirs[5] = {1, 1, -1, -1, 1};
        memset(f, -1, sizeof(f));

        auto dfs = [&](this auto&& dfs, int i, int j, int k, int cnt) -> int {
            if (f[i][j][k][cnt] != -1) {
                return f[i][j][k][cnt];
            }
            int x = i + dirs[k];
            int y = j + dirs[k + 1];
            int target = grid[i][j] == 1 ? 2 : (2 - grid[i][j]);
            if (x < 0 || x >= m || y < 0 || y >= n || grid[x][y] != target) {
                f[i][j][k][cnt] = 0;
                return 0;
            }
            int res = dfs(x, y, k, cnt);
            if (cnt > 0) {
                res = max(res, dfs(x, y, (k + 1) % 4, 0));
            }
            f[i][j][k][cnt] = 1 + res;
            return 1 + res;
        };

        int ans = 0;
        for (int i = 0; i < m; ++i) {
            for (int j = 0; j < n; ++j) {
                if (grid[i][j] == 1) {
                    for (int k = 0; k < 4; ++k) {
                        ans = max(ans, dfs(i, j, k, 1) + 1);
                    }
                }
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    private int m, n;
    private final int[] dirs = {1, 1, -1, -1, 1};
    private Integer[][][][] f;

    public int lenOfVDiagonal(int[][] grid) {
        m = grid.length;
        n = grid[0].length;
        f = new Integer[m][n][4][2];
        int ans = 0;
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                if (grid[i][j] == 1) {
                    for (int k = 0; k < 4; k++) {
                        ans = Math.max(ans, dfs(grid, i, j, k, 1) + 1);
                    }
                }
            }
        }
        return ans;
    }

    private int dfs(int[][] grid, int i, int j, int k, int cnt) {
        if (f[i][j][k][cnt] != null) {
            return f[i][j][k][cnt];
        }
        int x = i + dirs[k];
        int y = j + dirs[k + 1];
        int target = grid[i][j] == 1 ? 2 : (2 - grid[i][j]);
        if (x < 0 || x >= m || y < 0 || y >= n || grid[x][y] != target) {
            f[i][j][k][cnt] = 0;
            return 0;
        }
        int res = dfs(grid, x, y, k, cnt);
        if (cnt > 0) {
            res = Math.max(res, dfs(grid, x, y, (k + 1) % 4, 0));
        }
        f[i][j][k][cnt] = 1 + res;
        return 1 + res;
    }
}
```

## Code (Python3)

```python
class Solution:
    def lenOfVDiagonal(self, grid: List[List[int]]) -> int:
        @cache
        def dfs(i: int, j: int, k: int, cnt: int) -> int:
            x, y = i + dirs[k], j + dirs[k + 1]
            target = 2 if grid[i][j] == 1 else (2 - grid[i][j])
            if not 0 <= x < m or not 0 <= y < n or grid[x][y] != target:
                return 0
            res = dfs(x, y, k, cnt)
            if cnt > 0:
                res = max(res, dfs(x, y, (k + 1) % 4, 0))
            return 1 + res

        m, n = len(grid), len(grid[0])
        dirs = (1, 1, -1, -1, 1)
        ans = 0
        for i, row in enumerate(grid):
            for j, x in enumerate(row):
                if x == 1:
                    for k in range(4):
                        ans = max(ans, dfs(i, j, k, 1) + 1)
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
