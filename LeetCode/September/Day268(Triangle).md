--- ❤️ ---

# 🚀 _Day 268. Triangle_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/triangle/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int minimumTotal(vector<vector<int>>& triangle) {
        int n = triangle.size();
        vector<vector<int>> f(n + 1, vector<int>(n + 1, 0));
        for (int i = n - 1; i >= 0; --i) {
            for (int j = 0; j <= i; ++j) {
                f[i][j] = min(f[i + 1][j], f[i + 1][j + 1]) + triangle[i][j];
            }
        }
        return f[0][0];
    }
};
```

## Code (Java)

```java
class Solution {
    public int minimumTotal(List<List<Integer>> triangle) {
        int n = triangle.size();
        int[][] f = new int[n + 1][n + 1];
        for (int i = n - 1; i >= 0; --i) {
            for (int j = 0; j <= i; ++j) {
                f[i][j] = Math.min(f[i + 1][j], f[i + 1][j + 1]) + triangle.get(i).get(j);
            }
        }
        return f[0][0];
    }
}
```

## Code (Python)

```python
class Solution:
    def minimumTotal(self, triangle: List[List[int]]) -> int:
        n = len(triangle)
        f = [[0] * (n + 1) for _ in range(n + 1)]
        for i in range(n - 1, -1, -1):
            for j in range(i + 1):
                f[i][j] = min(f[i + 1][j], f[i + 1][j + 1]) + triangle[i][j]
        return f[0][0]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
