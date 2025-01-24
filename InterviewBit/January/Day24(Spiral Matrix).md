
# 🚀 _Day 24. Spiral Matrix_ 🧠

Problem Description
Given an array of A of length B×C.
Make a Spiral matrix (2D array) of B rows and C columns.

Note: See example input for pattern.

The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/spiral-matrix/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
using namespace std;

class Solution {
public:
    // Function to generate the spiral matrix
    vector<vector<int>> solve(vector<int>& A, int B, int C) {
        vector<vector<int>> matrix(B, vector<int>(C, 0)); // Initialize empty matrix
        int top = 0, bottom = B - 1, left = 0, right = C - 1;
        int index = 0;

        while (top <= bottom && left <= right) {
            // Fill top row
            for (int i = left; i <= right; ++i) {
                matrix[top][i] = A[index++];
            }
            top++;

            // Fill right column
            for (int i = top; i <= bottom; ++i) {
                matrix[i][right] = A[index++];
            }
            right--;

            if (top <= bottom) {
                // Fill bottom row
                for (int i = right; i >= left; --i) {
                    matrix[bottom][i] = A[index++];
                }
                bottom--;
            }

            if (left <= right) {
                // Fill left column
                for (int i = bottom; i >= top; --i) {
                    matrix[i][left] = A[index++];
                }
                left++;
            }
        }

        return matrix;
    }
};

```

## Code (Java)

```java
import java.util.*;

class Solution {
    // Function to generate the spiral matrix
    public int[][] solve(int[] A, int B, int C) {
        int[][] matrix = new int[B][C]; // Initialize empty matrix
        int top = 0, bottom = B - 1, left = 0, right = C - 1;
        int index = 0;

        while (top <= bottom && left <= right) {
            // Fill top row
            for (int i = left; i <= right; i++) {
                matrix[top][i] = A[index++];
            }
            top++;

            // Fill right column
            for (int i = top; i <= bottom; i++) {
                matrix[i][right] = A[index++];
            }
            right--;

            if (top <= bottom) {
                // Fill bottom row
                for (int i = right; i >= left; i--) {
                    matrix[bottom][i] = A[index++];
                }
                bottom--;
            }

            if (left <= right) {
                // Fill left column
                for (int i = bottom; i >= top; i--) {
                    matrix[i][left] = A[index++];
                }
                left++;
            }
        }

        return matrix;
    }
}

```

## Code (Python)

```python
class Solution:
    # @param A : list of integers
    # @param B : integer (number of rows)
    # @param C : integer (number of columns)
    # @return a list of list of integers
    def solve(self, A, B, C):
        matrix = [[0] * C for _ in range(B)]  # Initialize empty matrix
        top, bottom, left, right = 0, B - 1, 0, C - 1
        index = 0

        while top <= bottom and left <= right:
            # Fill top row
            for i in range(left, right + 1):
                matrix[top][i] = A[index]
                index += 1
            top += 1

            # Fill right column
            for i in range(top, bottom + 1):
                matrix[i][right] = A[index]
                index += 1
            right -= 1

            if top <= bottom:
                # Fill bottom row
                for i in range(right, left - 1, -1):
                    matrix[bottom][i] = A[index]
                    index += 1
                bottom -= 1

            if left <= right:
                # Fill left column
                for i in range(bottom, top - 1, -1):
                    matrix[i][left] = A[index]
                    index += 1
                left += 1

        return matrix

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
 <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>485</h4>
