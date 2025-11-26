--- ❤️ ---

# 🚀 _Day 330.  Paths in Matrix Whose Sum Is Divisible by K_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/paths-in-matrix-whose-sum-is-divisible-by-k/)

## 🎯 **My Approach:**


## Code(C++)
```cpp

```

## Code (Java)

```java

```

## Code (Python)

```python
class Solution:
    def numberOfPaths(self, grid: List[List[int]], k: int) -> int:
        @cache
        def dfs(i, j, s):
            if i < 0 or i >= m or j < 0 or j >= n:
                return 0
            s = (s + grid[i][j]) % k
            if i == m - 1 and j == n - 1:
                return int(s == 0)
            ans = dfs(i + 1, j, s) + dfs(i, j + 1, s)
            return ans % mod

        m, n = len(grid), len(grid[0])
        mod = 10**9 + 7
        ans = dfs(0, 0, 0)
        dfs.cache_clear()
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
