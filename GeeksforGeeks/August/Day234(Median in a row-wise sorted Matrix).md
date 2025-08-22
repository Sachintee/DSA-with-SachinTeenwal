---
title: "🔢 Median in a Row-wise Sorted Matrix | GFG Solution 🔍"
keywords🏷️: ["🔢 matrix median", "🔍 binary search", "📍 sorted matrix", "📈 upper bound", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to find median in a row-wise sorted matrix: efficiently find the median element using binary search on answer technique. 🚀"
date: 📅 2025-08-22
---

# *234. Median in a Row-wise Sorted Matrix*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/median-in-a-row-wise-sorted-matrix1527/1)

## **🧩 Problem Description**

Given a row-wise sorted matrix `mat[][]` of size `n*m`, where the number of rows and columns is always odd. Your task is to find the **median of the matrix**.

The median is the middle element when all matrix elements are arranged in sorted order. Since the total number of elements is always odd, there will be exactly one median element.


## Code(C++)
```cpp
class Solution {
public:
    int median(vector<vector<int>>& mat) {
        int n = mat.size(), m = mat[0].size();
        int lo = mat[0][0], hi = mat[0][m-1];
        for (int i = 1; i < n; i++) {
            lo = min(lo, mat[i][0]);
            hi = max(hi, mat[i][m-1]);
        }
        int req = (n * m + 1) >> 1;
        while (lo < hi) {
            int mid = lo + ((hi - lo) >> 1), cnt = 0;
            for (int i = 0; i < n; i++)
                cnt += upper_bound(mat[i].begin(), mat[i].end(), mid) - mat[i].begin();
            if (cnt < req) lo = mid + 1;
            else hi = mid;
        }
        return lo;
    }
};
```

## Code (Java)

```java
class Solution {
    public int median(int[][] mat) {
        int n = mat.length, m = mat[0].length;
        int lo = mat[0][0], hi = mat[0][m-1];
        for (int i = 1; i < n; i++) {
            lo = Math.min(lo, mat[i][0]);
            hi = Math.max(hi, mat[i][m-1]);
        }
        int req = (n * m + 1) / 2;
        while (lo < hi) {
            int mid = lo + (hi - lo) / 2, cnt = 0;
            for (int i = 0; i < n; i++) {
                int left = 0, right = m;
                while (left < right) {
                    int center = left + (right - left) / 2;
                    if (mat[i][center] <= mid) left = center + 1;
                    else right = center;
                }
                cnt += left;
            }
            if (cnt < req) lo = mid + 1;
            else hi = mid;
        }
        return lo;
    }
}
```

## Code (Python)

```python
import bisect
class Solution:
    def median(self, mat):
        n, m = len(mat), len(mat[0])
        lo = min(row[0] for row in mat)
        hi = max(row[m-1] for row in mat)
        req = (n * m + 1) // 2
        while lo < hi:
            mid = (lo + hi) // 2
            cnt = sum(bisect.bisect_right(row, mid) for row in mat)
            if cnt < req:
                lo = mid + 1
            else:
                hi = mid
        return lo
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
