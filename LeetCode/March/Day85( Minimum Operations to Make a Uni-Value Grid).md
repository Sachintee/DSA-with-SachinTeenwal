--- ❤️ ---

# 🚀 _Day 85.  Minimum Operations to Make a Uni-Value Grid_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/minimum-operations-to-make-a-uni-value-grid/submissions/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int minOperations(vector<vector<int>>& grid, int x) {
        int m = grid.size(), n = grid[0].size();
        int mod = grid[0][0] % x;
        int nums[m * n];
        for (int i = 0; i < m; ++i) {
            for (int j = 0; j < n; ++j) {
                if (grid[i][j] % x != mod) {
                    return -1;
                }
                nums[i * n + j] = grid[i][j];
            }
        }
        sort(nums, nums + m * n);
        int mid = nums[(m * n) >> 1];
        int ans = 0;
        for (int v : nums) {
            ans += abs(v - mid) / x;
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int minOperations(int[][] grid, int x) {
        int m = grid.length, n = grid[0].length;
        int[] nums = new int[m * n];
        int mod = grid[0][0] % x;
        for (int i = 0; i < m; ++i) {
            for (int j = 0; j < n; ++j) {
                if (grid[i][j] % x != mod) {
                    return -1;
                }
                nums[i * n + j] = grid[i][j];
            }
        }
        Arrays.sort(nums);
        int mid = nums[nums.length >> 1];
        int ans = 0;
        for (int v : nums) {
            ans += Math.abs(v - mid) / x;
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def minOperations(self, grid: List[List[int]], x: int) -> int:
        nums = []
        mod = grid[0][0] % x
        for row in grid:
            for v in row:
                if v % x != mod:
                    return -1
                nums.append(v)
        nums.sort()
        mid = nums[len(nums) >> 1]
        return sum(abs(v - mid) // x for v in nums)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
