---
title: "📐 Maximum Sum Rectangle | GFG Solution 🔍"
keywords🏷️: ["📐 maximum sum rectangle", "🔍 column compression", "🧠 dynamic programming",  "📍 kadane's algorithm", "📈 submatrix sum", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Maximum Sum Rectangle problem: find maximum possible sum of any submatrix using column compression and Kadane's algorithm. 🚀"
date: 📅 2025-08-04
---

# *216. Maximum Sum Rectangle*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/maximum-sum-rectangle2948/1)

## **🧩 Problem Description**

Given a 2D matrix `mat[][]` with dimensions `n×m`, find the **maximum possible sum** of any submatrix within the given matrix.

A submatrix is any contiguous rectangular region within the matrix. The goal is to find the submatrix with the largest sum of all its elements.


## Code(C++)
```cpp
class Solution {
public:
    int maxRectSum(vector<vector<int>>& mat) {
        int m = mat.size(), n = mat[0].size(), res = INT_MIN;
        for (int l = 0; l < n; l++) {
            vector<int> temp(m, 0);
            for (int r = l; r < n; r++) {
                for (int i = 0; i < m; i++) temp[i] += mat[i][r];
                int sum = 0, maxSum = temp[0];
                for (int x : temp) {
                    sum = max(x, sum + x);
                    maxSum = max(maxSum, sum);
                }
                res = max(res, maxSum);
            }
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public int maxRectSum(int mat[][]) {
        int m = mat.length, n = mat[0].length, res = Integer.MIN_VALUE;
        for (int l = 0; l < n; l++) {
            int[] temp = new int[m];
            for (int r = l; r < n; r++) {
                for (int i = 0; i < m; i++) temp[i] += mat[i][r];
                int sum = 0, maxSum = temp[0];
                for (int x : temp) {
                    sum = Math.max(x, sum + x);
                    maxSum = Math.max(maxSum, sum);
                }
                res = Math.max(res, maxSum);
            }
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def maxRectSum(self, mat):
        m, n, res = len(mat), len(mat[0]), float('-inf')
        for l in range(n):
            temp = [0] * m
            for r in range(l, n):
                for i in range(m):
                    temp[i] += mat[i][r]
                sum_val, max_sum = 0, temp[0]
                for x in temp:
                    sum_val = max(x, sum_val + x)
                    max_sum = max(max_sum, sum_val)
                res = max(res, max_sum)
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
