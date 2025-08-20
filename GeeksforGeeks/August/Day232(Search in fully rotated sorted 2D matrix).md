---
title: "🔍 Search in Fully Rotated Sorted 2D Matrix | GFG Solution 🎯"
keywords🏷️: ["🔍 matrix search", "🌀 rotated matrix", "📍 binary search", "📈 2D array", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to Search in Fully Rotated Sorted 2D Matrix: efficiently find target element in rotated sorted matrix using modified binary search technique. 🚀"
date: 📅 2025-08-20
---

# *232. Search in Fully Rotated Sorted 2D Matrix*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/search-in-fully-rotated-sorted-2d-matrix/1)

## **🧩 Problem Description**

You are given a 2D matrix `mat[][]` of size `n x m` that was initially filled in the following manner:

- Each row is sorted in increasing order from left to right.
- The first element of every row is greater than the last element of the previous row.

This implies that if the matrix is flattened row-wise, it forms a strictly sorted 1D array. Later, this sorted 1D array was rotated at some unknown pivot. The rotated array was then written back into the matrix row-wise to form the current matrix.

Given such a matrix `mat[][]` and an integer `x`, determine whether `x` exists in the matrix.


## Code(C++)
```cpp
class Solution {
public:
    bool searchMatrix(vector<vector<int>>& mat, int x) {
        int n = mat.size(), m = mat[0].size();
        int l = 0, r = n * m - 1;
        while (l <= r) {
            int mid = l + (r - l) / 2;
            int val = mat[mid / m][mid % m];
            if (val == x) return true;
            if (mat[l / m][l % m] <= val) {
                if (mat[l / m][l % m] <= x && x < val) r = mid - 1;
                else l = mid + 1;
            } else {
                if (val < x && x <= mat[r / m][r % m]) l = mid + 1;
                else r = mid - 1;
            }
        }
        return false;
    }
};
```

## Code (Java)

```java
class Solution {
    public boolean searchMatrix(int[][] mat, int x) {
        int n = mat.length, m = mat[0].length;
        int l = 0, r = n * m - 1;
        while (l <= r) {
            int mid = l + (r - l) / 2;
            int val = mat[mid / m][mid % m];
            if (val == x) return true;
            if (mat[l / m][l % m] <= val) {
                if (mat[l / m][l % m] <= x && x < val) r = mid - 1;
                else l = mid + 1;
            } else {
                if (val < x && x <= mat[r / m][r % m]) l = mid + 1;
                else r = mid - 1;
            }
        }
        return false;
    }
}
```

## Code (Python)

```python
class Solution:
    def searchMatrix(self, mat, x):
        n, m = len(mat), len(mat[0])
        l, r = 0, n * m - 1
        while l <= r:
            mid = l + (r - l) // 2
            val = mat[mid // m][mid % m]
            if val == x: return True
            if mat[l // m][l % m] <= val:
                if mat[l // m][l % m] <= x < val: r = mid - 1
                else: l = mid + 1
            else:
                if val < x <= mat[r // m][r % m]: l = mid + 1
                else: r = mid - 1
        return False
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
