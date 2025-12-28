--- ❤️ ---

# 🚀 _Day 362. Count Negative Numbers in a Sorted Matrix_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/count-negative-numbers-in-a-sorted-matrix/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int countNegatives(vector<vector<int>>& grid) {
        int m = grid.size();
        int n = grid[0].size();
        int i = m - 1;
        int j = 0;
        int ans = 0;
        while (i >= 0 && j < n) {
            if (grid[i][j] >= 0) {
                j++;
            } else {
                ans += n - j;
                i--;
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int countNegatives(int[][] grid) {
        int m = grid.length;
        int n = grid[0].length;
        int i = m - 1;
        int j = 0;
        int ans = 0;
        while (i >= 0 && j < n) {
            if (grid[i][j] >= 0) {
                j++;
            } else {
                ans += n - j;
                i--;
            }
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def countNegatives(self, grid: List[List[int]]) -> int:
        m, n = len(grid), len(grid[0])
        i, j = m - 1, 0
        ans = 0
        while i >= 0 and j < n:
            if grid[i][j] >= 0:
                j += 1
            else:
                ans += n - j
                i -= 1
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
