---
title: "🎨 Make Matrix Beautiful | GFG Solution ✨"
keywords🏷️: ["🎨 matrix manipulation", "🔄 optimization", "📊 row column sum", "🧮 greedy algorithm", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to Make Matrix Beautiful problem: find minimum operations to make all row and column sums equal using greedy optimization approach. 🚀"
date: 📅 2025-07-28
---

# *209. Make Matrix Beautiful*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/make-matrix-beautiful-1587115620/1)

## **🧩 Problem Description**

A beautiful matrix is defined as a square matrix in which the **sum of elements in every row and every column is equal**. Given a square matrix `mat[][]`, your task is to determine the minimum number of operations required to make the matrix beautiful.

In one operation, you are allowed to **increment the value of any single cell by 1**.


## Code(C++)
```cpp
class Solution {
public:
    int balanceSums(vector<vector<int>>& mat) {
        int n = mat.size(), max = 0, res = 0;
        for (int i = 0; i < n; i++) {
            int sum = 0;
            for (int j = 0; j < n; j++) sum += mat[i][j];
            max = sum > max ? sum : max;
        }
        for (int j = 0; j < n; j++) {
            int sum = 0;
            for (int i = 0; i < n; i++) sum += mat[i][j];
            max = sum > max ? sum : max;
        }
        for (int i = 0; i < n; i++) {
            int sum = 0;
            for (int j = 0; j < n; j++) sum += mat[i][j];
            res += max - sum;
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public static int balanceSums(int[][] mat) {
        int n = mat.length, max = 0, res = 0;
        for (int i = 0; i < n; i++) {
            int sum = 0;
            for (int j = 0; j < n; j++) sum += mat[i][j];
            max = Math.max(sum, max);
        }
        for (int j = 0; j < n; j++) {
            int sum = 0;
            for (int i = 0; i < n; i++) sum += mat[i][j];
            max = Math.max(sum, max);
        }
        for (int i = 0; i < n; i++) {
            int sum = 0;
            for (int j = 0; j < n; j++) sum += mat[i][j];
            res += max - sum;
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def balanceSums(self, mat):
        n, max_sum, res = len(mat), 0, 0
        for i in range(n):
            sum_val = sum(mat[i])
            max_sum = max(sum_val, max_sum)
        for j in range(n):
            sum_val = sum(mat[i][j] for i in range(n))
            max_sum = max(sum_val, max_sum)
        for i in range(n):
            res += max_sum - sum(mat[i])
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
