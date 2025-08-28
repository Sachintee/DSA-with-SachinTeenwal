--- ❤️ ---

# 🚀 _Day 240. Sort Matrix by Diagonals_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/sort-matrix-by-diagonals/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    vector<vector<int>> sortMatrix(vector<vector<int>>& grid) {
        int n = grid.size();
        for (int k = n - 2; k >= 0; --k) {
            int i = k, j = 0;
            vector<int> t;
            while (i < n && j < n) {
                t.push_back(grid[i++][j++]);
            }
            ranges::sort(t);
            for (int x : t) {
                grid[--i][--j] = x;
            }
        }
        for (int k = n - 2; k > 0; --k) {
            int i = k, j = n - 1;
            vector<int> t;
            while (i >= 0 && j >= 0) {
                t.push_back(grid[i--][j--]);
            }
            ranges::sort(t);
            for (int x : t) {
                grid[++i][++j] = x;
            }
        }
        return grid;
    }
};
```

## Code (Java)

```java
class Solution {
    public int[][] sortMatrix(int[][] grid) {
        int n = grid.length;
        for (int k = n - 2; k >= 0; --k) {
            int i = k, j = 0;
            List<Integer> t = new ArrayList<>();
            while (i < n && j < n) {
                t.add(grid[i++][j++]);
            }
            Collections.sort(t);
            for (int x : t) {
                grid[--i][--j] = x;
            }
        }
        for (int k = n - 2; k > 0; --k) {
            int i = k, j = n - 1;
            List<Integer> t = new ArrayList<>();
            while (i >= 0 && j >= 0) {
                t.add(grid[i--][j--]);
            }
            Collections.sort(t);
            for (int x : t) {
                grid[++i][++j] = x;
            }
        }
        return grid;
    }
}
```

## Code (Python3)

```python
class Solution:
    def sortMatrix(self, grid: List[List[int]]) -> List[List[int]]:
        n = len(grid)
        for k in range(n - 2, -1, -1):
            i, j = k, 0
            t = []
            while i < n and j < n:
                t.append(grid[i][j])
                i += 1
                j += 1
            t.sort()
            i, j = k, 0
            while i < n and j < n:
                grid[i][j] = t.pop()
                i += 1
                j += 1
        for k in range(n - 2, 0, -1):
            i, j = k, n - 1
            t = []
            while i >= 0 and j >= 0:
                t.append(grid[i][j])
                i -= 1
                j -= 1
            t.sort()
            i, j = k, n - 1
            while i >= 0 and j >= 0:
                grid[i][j] = t.pop()
                i -= 1
                j -= 1
        return grid
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
