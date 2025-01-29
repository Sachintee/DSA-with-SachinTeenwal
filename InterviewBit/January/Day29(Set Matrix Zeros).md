--- ❤️ ---
# 🚀 _Day 29. Set Matrix Zeros_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/set-matrix-zeros/)
Problem Description

Given a matrix, A of size M x N of 0s and 1s. If an element is 0, set its entire row and column to 0.
Note: This will be evaluated on the extra memory used. Try to minimize the space and time complexity.



## Code(C++)
```cpp
#include <iostream>
#include <vector>
using namespace std;

class Solution {
public:
    void setZeroes(vector<vector<int>>& A) {
        int rows = A.size(), cols = A[0].size();
        bool firstRowZero = false, firstColZero = false;

        // Check if first row needs to be zero
        for (int j = 0; j < cols; j++) {
            if (A[0][j] == 0) {
                firstRowZero = true;
                break;
            }
        }

        // Check if first column needs to be zero
        for (int i = 0; i < rows; i++) {
            if (A[i][0] == 0) {
                firstColZero = true;
                break;
            }
        }

        // Use first row and first column as markers
        for (int i = 1; i < rows; i++) {
            for (int j = 1; j < cols; j++) {
                if (A[i][j] == 0) {
                    A[i][0] = 0;
                    A[0][j] = 0;
                }
            }
        }

        // Set matrix cells to zero based on markers
        for (int i = 1; i < rows; i++) {
            for (int j = 1; j < cols; j++) {
                if (A[i][0] == 0 || A[0][j] == 0) {
                    A[i][j] = 0;
                }
            }
        }

        // Update first row if needed
        if (firstRowZero) {
            for (int j = 0; j < cols; j++) {
                A[0][j] = 0;
            }
        }

        // Update first column if needed
        if (firstColZero) {
            for (int i = 0; i < rows; i++) {
                A[i][0] = 0;
            }
        }
    }
};

// Driver Code
int main() {
    Solution obj;
    vector<vector<int>> A = {{1, 0, 1}, {1, 1, 1}, {1, 1, 1}};
    obj.setZeroes(A);

    for (auto row : A) {
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
    public void setZeroes(int[][] A) {
        int rows = A.length, cols = A[0].length;
        boolean firstRowZero = false, firstColZero = false;

        // Check if first row needs to be zero
        for (int j = 0; j < cols; j++) {
            if (A[0][j] == 0) {
                firstRowZero = true;
                break;
            }
        }

        // Check if first column needs to be zero
        for (int i = 0; i < rows; i++) {
            if (A[i][0] == 0) {
                firstColZero = true;
                break;
            }
        }

        // Use first row and column as markers
        for (int i = 1; i < rows; i++) {
            for (int j = 1; j < cols; j++) {
                if (A[i][j] == 0) {
                    A[i][0] = 0;
                    A[0][j] = 0;
                }
            }
        }

        // Set matrix cells to zero based on markers
        for (int i = 1; i < rows; i++) {
            for (int j = 1; j < cols; j++) {
                if (A[i][0] == 0 || A[0][j] == 0) {
                    A[i][j] = 0;
                }
            }
        }

        // Update first row if needed
        if (firstRowZero) {
            for (int j = 0; j < cols; j++) {
                A[0][j] = 0;
            }
        }

        // Update first column if needed
        if (firstColZero) {
            for (int i = 0; i < rows; i++) {
                A[i][0] = 0;
            }
        }
    }

    // Driver Code
    public static void main(String[] args) {
        Solution obj = new Solution();
        int[][] A = {{1, 0, 1}, {1, 1, 1}, {1, 1, 1}};
        obj.setZeroes(A);

        for (int[] row : A) {
            System.out.println(Arrays.toString(row));
        }
    }
}

```

## Code (Python)

```python
class Solution:
    def setZeroes(self, A):
        rows, cols = len(A), len(A[0])
        first_row_zero, first_col_zero = False, False

        # Check if first row needs to be set to zero
        for j in range(cols):
            if A[0][j] == 0:
                first_row_zero = True
                break
        
        # Check if first column needs to be set to zero
        for i in range(rows):
            if A[i][0] == 0:
                first_col_zero = True
                break
        
        # Use first row & column to mark zero positions
        for i in range(1, rows):
            for j in range(1, cols):
                if A[i][j] == 0:
                    A[i][0] = 0
                    A[0][j] = 0

        # Set matrix cells to zero based on markers
        for i in range(1, rows):
            for j in range(1, cols):
                if A[i][0] == 0 or A[0][j] == 0:
                    A[i][j] = 0

        # Set first row to zero if needed
        if first_row_zero:
            for j in range(cols):
                A[0][j] = 0

        # Set first column to zero if needed
        if first_col_zero:
            for i in range(rows):
                A[i][0] = 0

        return A

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
 <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>856</h4>
