--- ❤️ ---

# 🚀 _Day 359. Find the Peak Element in a 2D Matrix_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/find-the-peak-element-in-a-2d-matrix/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    vector<int> findPeakGrid(vector<vector<int>>& mat) {
        int n = mat.size();
        int m = mat[0].size();

        int left = 0, right = m - 1;

        while (left <= right) {
            int mid = left + (right - left) / 2;

            // Find row index of maximum element in mid column
            int maxRow = 0;
            for (int i = 0; i < n; i++) {
                if (mat[i][mid] > mat[maxRow][mid]) {
                    maxRow = i;
                }
            }

            int leftVal  = (mid > 0)     ? mat[maxRow][mid - 1] : -1e9;
            int rightVal = (mid < m - 1) ? mat[maxRow][mid + 1] : -1e9;

            // Check peak condition
            if (mat[maxRow][mid] >= leftVal &&
                mat[maxRow][mid] >= rightVal) {
                return {maxRow, mid};
            }
            else if (leftVal > mat[maxRow][mid]) {
                right = mid - 1;
            }
            else {
                left = mid + 1;
            }
        }

        return {-1, -1}; // never reached
    }
};

```

## Code (Java)

```java
class Solution {
    public int[] findPeakGrid(int[][] mat) {
        int n = mat.length;
        int m = mat[0].length;

        int left = 0, right = m - 1;

        while (left <= right) {
            int mid = left + (right - left) / 2;

            // Find row index of maximum element in mid column
            int maxRow = 0;
            for (int i = 0; i < n; i++) {
                if (mat[i][mid] > mat[maxRow][mid]) {
                    maxRow = i;
                }
            }

            int leftVal  = (mid > 0)     ? mat[maxRow][mid - 1] : Integer.MIN_VALUE;
            int rightVal = (mid < m - 1) ? mat[maxRow][mid + 1] : Integer.MIN_VALUE;

            // Check peak condition
            if (mat[maxRow][mid] >= leftVal && mat[maxRow][mid] >= rightVal) {
                return new int[]{maxRow, mid};
            } 
            else if (leftVal > mat[maxRow][mid]) {
                right = mid - 1;
            } 
            else {
                left = mid + 1;
            }
        }

        return new int[]{-1, -1}; // never reached
    }
}

```

## Code (Python)

```python
class Solution:
    def findPeakGrid(self, mat):
        n = len(mat)
        m = len(mat[0])

        left, right = 0, m - 1

        while left <= right:
            mid = (left + right) // 2

            # Find row index of maximum element in mid column
            max_row = 0
            for i in range(n):
                if mat[i][mid] > mat[max_row][mid]:
                    max_row = i

            left_val = mat[max_row][mid - 1] if mid > 0 else float('-inf')
            right_val = mat[max_row][mid + 1] if mid < m - 1 else float('-inf')

            # Peak found
            if mat[max_row][mid] >= left_val and mat[max_row][mid] >= right_val:
                return [max_row, mid]
            elif left_val > mat[max_row][mid]:
                right = mid - 1
            else:
                left = mid + 1

        return [-1, -1]  # never reached

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
