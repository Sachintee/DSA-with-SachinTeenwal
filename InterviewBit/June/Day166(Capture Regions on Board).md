--- ❤️ ---

# 🚀 _Day 166. Capture Regions on Board_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/capture-regions-on-board/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <utility>

using namespace std;

class Solution {
public:
    void solve(vector<vector<char>>& board) {
        if (board.empty()) return;
        
        int rows = board.size();
        int cols = board[0].size();
        
        // Directions: up, down, left, right
        vector<pair<int, int>> directions = {{-1, 0}, {1, 0}, {0, -1}, {0, 1}};
        
        // DFS function to mark boundary-connected 'O's
        function<void(int, int)> dfs = [&](int i, int j) {
            if (i < 0 || i >= rows || j < 0 || j >= cols || board[i][j] != 'O') {
                return;
            }
            board[i][j] = 'B'; // Mark as boundary-connected
            for (auto& dir : directions) {
                dfs(i + dir.first, j + dir.second);
            }
        };
        
        // Check first and last columns
        for (int i = 0; i < rows; ++i) {
            if (board[i][0] == 'O') dfs(i, 0);
            if (cols > 1 && board[i][cols - 1] == 'O') dfs(i, cols - 1);
        }
        
        // Check first and last rows
        for (int j = 0; j < cols; ++j) {
            if (board[0][j] == 'O') dfs(0, j);
            if (rows > 1 && board[rows - 1][j] == 'O') dfs(rows - 1, j);
        }
        
        // Flip remaining 'O's to 'X's and revert 'B's to 'O's
        for (int i = 0; i < rows; ++i) {
            for (int j = 0; j < cols; ++j) {
                if (board[i][j] == 'O') {
                    board[i][j] = 'X';
                } else if (board[i][j] == 'B') {
                    board[i][j] = 'O';
                }
            }
        }
    }
};
```

## Code (Java)

```java
class Solution {
    public void solve(char[][] board) {
        if (board == null || board.length == 0) return;
        
        int rows = board.length;
        int cols = board[0].length;
        
        // Directions: up, down, left, right
        int[][] directions = {{-1, 0}, {1, 0}, {0, -1}, {0, 1}};
        
        // DFS function to mark boundary-connected 'O's
        for (int i = 0; i < rows; i++) {
            if (board[i][0] == 'O') dfs(board, i, 0, directions);
            if (cols > 1 && board[i][cols - 1] == 'O') dfs(board, i, cols - 1, directions);
        }
        
        for (int j = 0; j < cols; j++) {
            if (board[0][j] == 'O') dfs(board, 0, j, directions);
            if (rows > 1 && board[rows - 1][j] == 'O') dfs(board, rows - 1, j, directions);
        }
        
        // Flip remaining 'O's to 'X's and revert 'B's to 'O's
        for (int i = 0; i < rows; i++) {
            for (int j = 0; j < cols; j++) {
                if (board[i][j] == 'O') {
                    board[i][j] = 'X';
                } else if (board[i][j] == 'B') {
                    board[i][j] = 'O';
                }
            }
        }
    }
    
    private void dfs(char[][] board, int i, int j, int[][] directions) {
        if (i < 0 || i >= board.length || j < 0 || j >= board[0].length || board[i][j] != 'O') {
            return;
        }
        board[i][j] = 'B'; // Mark as boundary-connected
        for (int[] dir : directions) {
            dfs(board, i + dir[0], j + dir[1], directions);
        }
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : list of list of chars
    def solve(self, A):
        if not A:
            return A
        
        rows = len(A)
        cols = len(A[0]) if rows > 0 else 0
        
        # Directions for moving in four possible directions (up, down, left, right)
        directions = [(-1, 0), (1, 0), (0, -1), (0, 1)]
        
        def dfs(i, j):
            if i < 0 or i >= rows or j < 0 or j >= cols or A[i][j] != 'O':
                return
            A[i][j] = 'B'  # Mark as boundary-connected
            for di, dj in directions:
                dfs(i + di, j + dj)
        
        # Check the first and last columns
        for i in range(rows):
            if A[i][0] == 'O':
                dfs(i, 0)
            if cols > 1 and A[i][cols - 1] == 'O':
                dfs(i, cols - 1)
        
        # Check the first and last rows
        for j in range(cols):
            if A[0][j] == 'O':
                dfs(0, j)
            if rows > 1 and A[rows - 1][j] == 'O':
                dfs(rows - 1, j)
        
        # Flip all remaining 'O's to 'X's and revert 'B's back to 'O's
        for i in range(rows):
            for j in range(cols):
                if A[i][j] == 'O':
                    A[i][j] = 'X'
                elif A[i][j] == 'B':
                    A[i][j] = 'O'
        
        return A
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
