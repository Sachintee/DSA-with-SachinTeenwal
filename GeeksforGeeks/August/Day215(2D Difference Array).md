---
title: "🔢 2D Difference Array | GFG Solution 🔍"
keywords🏷️: ["🔢 2D difference array", "🔍 range updates", "📍 prefix sum", "📈 matrix operations", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the 2D Difference Array problem: efficiently apply multiple range updates on 2D matrix using difference array technique with 2D prefix sum optimization. 🚀"
date: 📅 2025-08-03
---

# *215. 2D Difference Array*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/2-d-difference-array/1)

## **🧩 Problem Description**

You are given a 2D integer matrix `mat[][]` of size `n × m` and a list of `q` operations `opr[][]`. Each operation is represented as an array `[v, r1, c1, r2, c2]`, where:

- `v` is the value to be added
- `(r1, c1)` is the top-left cell of a submatrix
- `(r2, c2)` is the bottom-right cell of the submatrix (inclusive)

For each of the `q` operations, add `v` to every element in the submatrix from `(r1, c1)` to `(r2, c2)`. Return the final matrix after applying all operations.


## Code(C++)
```cpp
class Solution {
public:
    vector<vector<int>> applyDiff2D(vector<vector<int>>& mat, vector<vector<int>>& opr) {
        int n = mat.size(), m = mat[0].size();
        vector<vector<int>> d(n + 1, vector<int>(m + 1, 0));
        
        for (auto& q : opr) {
            int v = q[0], r1 = q[1], c1 = q[2], r2 = q[3], c2 = q[4];
            d[r1][c1] += v;
            d[r1][c2 + 1] -= v;
            d[r2 + 1][c1] -= v;
            d[r2 + 1][c2 + 1] += v;
        }
        
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < m; j++) {
                if (i) d[i][j] += d[i - 1][j];
                if (j) d[i][j] += d[i][j - 1];
                if (i && j) d[i][j] -= d[i - 1][j - 1];
                mat[i][j] += d[i][j];
            }
        }
        return mat;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<ArrayList<Integer>> applyDiff2D(int[][] mat, int[][] opr) {
        int n = mat.length, m = mat[0].length;
        long[][] d = new long[n + 1][m + 1];
        
        for (int[] op : opr) {
            int v = op[0], r1 = op[1], c1 = op[2], r2 = op[3], c2 = op[4];
            d[r1][c1] += v;
            d[r1][c2 + 1] -= v;
            d[r2 + 1][c1] -= v;
            d[r2 + 1][c2 + 1] += v;
        }
        
        ArrayList<ArrayList<Integer>> res = new ArrayList<>();
        for (int i = 0; i < n; i++) {
            ArrayList<Integer> row = new ArrayList<>();
            for (int j = 0; j < m; j++) {
                if (i > 0) d[i][j] += d[i - 1][j];
                if (j > 0) d[i][j] += d[i][j - 1];
                if (i > 0 && j > 0) d[i][j] -= d[i - 1][j - 1];
                row.add(mat[i][j] + (int)d[i][j]);
            }
            res.add(row);
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def applyDiff2D(self, mat, opr):
        n, m = len(mat), len(mat[0])
        d = [[0] * (m + 1) for _ in range(n + 1)]
        
        for v, r1, c1, r2, c2 in opr:
            d[r1][c1] += v
            d[r1][c2 + 1] -= v
            d[r2 + 1][c1] -= v
            d[r2 + 1][c2 + 1] += v
        
        for i in range(n):
            for j in range(m):
                if i: d[i][j] += d[i - 1][j]
                if j: d[i][j] += d[i][j - 1]
                if i and j: d[i][j] -= d[i - 1][j - 1]
                mat[i][j] += d[i][j]
        return mat
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
