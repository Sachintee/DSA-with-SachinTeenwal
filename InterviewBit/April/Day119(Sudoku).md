--- ❤️ ---

# 🚀 _Day 119. Sudoku_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/sudoku/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <string>

using namespace std;

class Solution {
public:
    void solveSudoku(vector<vector<char>>& board) {
        backtrack(board);
    }
    
private:
    bool isValid(vector<vector<char>>& board, int row, int col, char num) {
        for (int i = 0; i < 9; ++i) {
            if (board[row][i] == num) return false;
            if (board[i][col] == num) return false;
        }
        int startRow = 3 * (row / 3);
        int startCol = 3 * (col / 3);
        for (int i = 0; i < 3; ++i) {
            for (int j = 0; j < 3; ++j) {
                if (board[startRow + i][startCol + j] == num) return false;
            }
        }
        return true;
    }
    
    bool backtrack(vector<vector<char>>& board) {
        for (int i = 0; i < 9; ++i) {
            for (int j = 0; j < 9; ++j) {
                if (board[i][j] == '.') {
                    for (char num = '1'; num <= '9'; ++num) {
                        if (isValid(board, i, j, num)) {
                            board[i][j] = num;
                            if (backtrack(board)) return true;
                            board[i][j] = '.';
                        }
                    }
                    return false;
                }
            }
        }
        return true;
    }
};
```

## Code (Java)

```java
class Solution {
    public void solveSudoku(char[][] board) {
        backtrack(board);
    }
    
    private boolean isValid(char[][] board, int row, int col, char num) {
        for (int i = 0; i < 9; ++i) {
            if (board[row][i] == num) return false;
            if (board[i][col] == num) return false;
        }
        int startRow = 3 * (row / 3);
        int startCol = 3 * (col / 3);
        for (int i = 0; i < 3; ++i) {
            for (int j = 0; j < 3; ++j) {
                if (board[startRow + i][startCol + j] == num) return false;
            }
        }
        return true;
    }
    
    private boolean backtrack(char[][] board) {
        for (int i = 0; i < 9; ++i) {
            for (int j = 0; j < 9; ++j) {
                if (board[i][j] == '.') {
                    for (char num = '1'; num <= '9'; ++num) {
                        if (isValid(board, i, j, num)) {
                            board[i][j] = num;
                            if (backtrack(board)) return true;
                            board[i][j] = '.';
                        }
                    }
                    return false;
                }
            }
        }
        return true;
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : list of list of chars
    # @return nothing
    def solveSudoku(self, A):
        def is_valid(A, row, col, num):
            # Check row
            for i in range(9):
                if A[row][i] == num:
                    return False
            # Check column
            for i in range(9):
                if A[i][col] == num:
                    return False
            # Check 3x3 subgrid
            start_row, start_col = 3 * (row // 3), 3 * (col // 3)
            for i in range(3):
                for j in range(3):
                    if A[start_row + i][start_col + j] == num:
                        return False
            return True
        
        def backtrack(A):
            for i in range(9):
                for j in range(9):
                    if A[i][j] == '.':
                        for num in map(str, range(1, 10)):
                            if is_valid(A, i, j, num):
                                A[i][j] = num
                                if backtrack(A):
                                    return True
                                A[i][j] = '.'
                        return False
            return True
        
        backtrack(A)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
