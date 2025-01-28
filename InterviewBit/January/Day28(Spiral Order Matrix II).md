--- ❤️ ---

# 🚀 _Day 28. Spiral Order Matrix II_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/spiral-order-matrix-ii/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <vector>
using namespace std;

class Solution {
public:
    vector<vector<int>> generateMatrix(int A) {
        vector<vector<int>> matrix(A, vector<int>(A, 0));
        int top = 0, left = 0, bottom = A - 1, right = A - 1, num = 1;

        while (top <= bottom && left <= right) {
            // Fill top row
            for (int col = left; col <= right; col++) {
                matrix[top][col] = num++;
            }
            top++;

            // Fill right column
            for (int row = top; row <= bottom; row++) {
                matrix[row][right] = num++;
            }
            right--;

            // Fill bottom row (if within bounds)
            if (top <= bottom) {
                for (int col = right; col >= left; col--) {
                    matrix[bottom][col] = num++;
                }
                bottom--;
            }

            // Fill left column (if within bounds)
            if (left <= right) {
                for (int row = bottom; row >= top; row--) {
                    matrix[row][left] = num++;
                }
                left++;
            }
        }
        return matrix;
    }
};

int main() {
    Solution solution;
    int A = 5;
    vector<vector<int>> result = solution.generateMatrix(A);

    // Print the matrix
    for (const auto& row : result) {
        for (int num : row) {
            cout << num << " ";
        }
        cout << endl;
    }
    return 0;
}

```

## Code (Java)

```java
import java.util.*;

class Solution {
    public int[][] generateMatrix(int A) {
        int[][] matrix = new int[A][A];
        int top = 0, left = 0, bottom = A - 1, right = A - 1, num = 1;

        while (top <= bottom && left <= right) {
            // Fill top row
            for (int col = left; col <= right; col++) {
                matrix[top][col] = num++;
            }
            top++;

            // Fill right column
            for (int row = top; row <= bottom; row++) {
                matrix[row][right] = num++;
            }
            right--;

            // Fill bottom row (if within bounds)
            if (top <= bottom) {
                for (int col = right; col >= left; col--) {
                    matrix[bottom][col] = num++;
                }
                bottom--;
            }

            // Fill left column (if within bounds)
            if (left <= right) {
                for (int row = bottom; row >= top; row--) {
                    matrix[row][left] = num++;
                }
                left++;
            }
        }
        return matrix;
    }

    public static void main(String[] args) {
        Solution solution = new Solution();
        int A = 5;
        int[][] result = solution.generateMatrix(A);

        // Print the matrix
        for (int i = 0; i < result.length; i++) {
            for (int j = 0; j < result[i].length; j++) {
                System.out.print(result[i][j] + " ");
            }
            System.out.println();
        }
    }
}

```

## Code (Python)

```python
class Solution:
    # @param A : integer
    # @return a list of list of integers
    def generateMatrix(self, A):
        matrix = [[0] * A for _ in range(A)]  # Create an empty A x A matrix
        top, left, bottom, right = 0, 0, A - 1, A - 1  # Boundaries
        num = 1

        while top <= bottom and left <= right:
            # Fill top row
            for col in range(left, right + 1):
                matrix[top][col] = num
                num += 1
            top += 1

            # Fill right column
            for row in range(top, bottom + 1):
                matrix[row][right] = num
                num += 1
            right -= 1

            # Fill bottom row (if within bounds)
            if top <= bottom:
                for col in range(right, left - 1, -1):
                    matrix[bottom][col] = num
                    num += 1
                bottom -= 1

            # Fill left column (if within bounds)
            if left <= right:
                for row in range(bottom, top - 1, -1):
                    matrix[row][left] = num
                    num += 1
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
   <h4>959</h4>
