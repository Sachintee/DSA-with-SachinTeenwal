--- ❤️ ---

# 🚀 _Day 234. Find the Minimum Area to Cover All Ones I_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/find-the-minimum-area-to-cover-all-ones-i/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int minimumArea(vector<vector<int>>& grid) {
        int m = grid.size(), n = grid[0].size();
        int x1 = m, y1 = n;
        int x2 = 0, y2 = 0;
        for (int i = 0; i < m; ++i) {
            for (int j = 0; j < n; ++j) {
                if (grid[i][j] == 1) {
                    x1 = min(x1, i);
                    y1 = min(y1, j);
                    x2 = max(x2, i);
                    y2 = max(y2, j);
                }
            }
        }
        return (x2 - x1 + 1) * (y2 - y1 + 1);
    }
};
```

## Code (Java)

```java
class Solution {
    public int minimumArea(int[][] grid) {
        int m = grid.length, n = grid[0].length;
        int x1 = m, y1 = n;
        int x2 = 0, y2 = 0;
        for (int i = 0; i < m; ++i) {
            for (int j = 0; j < n; ++j) {
                if (grid[i][j] == 1) {
                    x1 = Math.min(x1, i);
                    y1 = Math.min(y1, j);
                    x2 = Math.max(x2, i);
                    y2 = Math.max(y2, j);
                }
            }
        }
        return (x2 - x1 + 1) * (y2 - y1 + 1);
    }
}
```

## Code (Python)

```python
class Solution:
    def minimumArea(self, grid: List[List[int]]) -> int:
        x1 = y1 = inf
        x2 = y2 = -inf
        for i, row in enumerate(grid):
            for j, x in enumerate(row):
                if x == 1:
                    x1 = min(x1, i)
                    y1 = min(y1, j)
                    x2 = max(x2, i)
                    y2 = max(y2, j)
        return (x2 - x1 + 1) * (y2 - y1 + 1)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
