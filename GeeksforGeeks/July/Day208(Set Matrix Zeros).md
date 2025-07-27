---
title: "⚙️ Set Matrix Zeroes | GFG Solution 🔍"
keywords🏷️: ["⚙️ matrix manipulation", "🔍 in-place algorithm", "📍 space optimization", "📈 2D array", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Set Matrix Zeroes problem: modify matrix to set entire rows and columns to zero when encountering a zero element using optimal space approach. 🚀"
date: 📅 2025-07-27
---

# *208. Set Matrix Zeroes*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/set-matrix-zeroes/1)

## **🧩 Problem Description**

You are given a 2D matrix `mat[][]` of size `n x m`. The task is to modify the matrix such that if `mat[i][j]` is 0, all the elements in the **i-th row** and **j-th column** are set to 0.

The challenge is to solve this **in-place** without using extra space proportional to the matrix size.


## Code(C++)
```cpp
class Solution {
public:
    void setMatrixZeroes(vector<vector<int>>& mat) {
        int n = mat.size(), m = mat[0].size();
        bool firstRow = false, firstCol = false;
        for (int i = 0; i < n; ++i) firstCol |= mat[i][0] == 0;
        for (int j = 0; j < m; ++j) firstRow |= mat[0][j] == 0;
        for (int i = 1; i < n; ++i)
            for (int j = 1; j < m; ++j)
                if (mat[i][j] == 0)
                    mat[i][0] = mat[0][j] = 0;
        for (int i = 1; i < n; ++i)
            for (int j = 1; j < m; ++j)
                if (!mat[i][0] || !mat[0][j])
                    mat[i][j] = 0;
        if (firstRow) fill(begin(mat[0]), end(mat[0]), 0);
        if (firstCol) for (int i = 0; i < n; ++i) mat[i][0] = 0;
    }
};
```

## Code (Java)

```java
class Solution {
    public void setMatrixZeroes(int[][] mat) {
        int n = mat.length, m = mat[0].length;
        boolean row0 = false, col0 = false;
        for (int i = 0; i < n; i++) if (mat[i][0] == 0) col0 = true;
        for (int j = 0; j < m; j++) if (mat[0][j] == 0) row0 = true;
        for (int i = 1; i < n; i++)
            for (int j = 1; j < m; j++)
                if (mat[i][j] == 0)
                    mat[i][0] = mat[0][j] = 0;
        for (int i = 1; i < n; i++)
            for (int j = 1; j < m; j++)
                if (mat[i][0] == 0 || mat[0][j] == 0)
                    mat[i][j] = 0;
        if (row0) Arrays.fill(mat[0], 0);
        if (col0) for (int i = 0; i < n; i++) mat[i][0] = 0;
    }
}
```

## Code (Python)

```python
class Solution:
    def setMatrixZeroes(self, mat):
        n, m = len(mat), len(mat[0])
        row0 = any(mat[0][j] == 0 for j in range(m))
        col0 = any(mat[i][0] == 0 for i in range(n))
        for i in range(1, n):
            for j in range(1, m):
                if mat[i][j] == 0:
                    mat[i][0] = mat[0][j] = 0
        for i in range(1, n):
            for j in range(1, m):
                if mat[i][0] == 0 or mat[0][j] == 0:
                    mat[i][j] = 0
        if row0:
            for j in range(m): mat[0][j] = 0
        if col0:
            for i in range(n): mat[i][0] = 0
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
