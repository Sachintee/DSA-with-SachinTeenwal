# *151. Kth Element in Matrix*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/kth-element-in-matrix/1)

## **🧩 Problem Description**

Given a `n x n` matrix in which **each row and column is sorted in ascending order**, find the **kth smallest element** in the matrix.


## Code(C++)
```cpp
class Solution {
  public:
    int kthSmallest(vector<vector<int>>& matrix, int k) {
        int n = matrix.size(), l = matrix[0][0], r = matrix[n-1][n-1];
        while (l < r) {
            int m = l + (r - l) / 2, cnt = 0;
            for (int i = 0, j = n - 1; i < n; ++i) {
                while (j >= 0 && matrix[i][j] > m) --j;
                cnt += j + 1;
            }
            if (cnt < k) l = m + 1;
            else r = m;
        }
        return l;
    }
};
```

## Code (Java)

```java
class Solution {
    public int kthSmallest(int[][] matrix, int k) {
        int n = matrix.length, l = matrix[0][0], r = matrix[n - 1][n - 1];
        while (l < r) {
            int m = l + (r - l) / 2, cnt = 0, j = n - 1;
            for (int i = 0; i < n; ++i) {
                while (j >= 0 && matrix[i][j] > m) --j;
                cnt += j + 1;
            }
            if (cnt < k) l = m + 1;
            else r = m;
        }
        return l;
    }
}
```

## Code (Python)

```python
class Solution:
    def kthSmallest(self, matrix, k):
        n, l, r = len(matrix), matrix[0][0], matrix[-1][-1]
        while l < r:
            m = (l + r) // 2
            cnt, j = 0, n - 1
            for i in range(n):
                while j >= 0 and matrix[i][j] > m:
                    j -= 1
                cnt += j + 1
            if cnt < k:
                l = m + 1
            else:
                r = m
        return l
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
