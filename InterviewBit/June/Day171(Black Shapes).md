--- ❤️ ---

# 🚀 _Day 171. Black Shapes_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/black-shapes/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <string>
using namespace std;

class Solution {
public:
    int black(vector<string> &A) {
        if (A.empty()) return 0;
        
        int rows = A.size();
        int cols = A[0].size();
        vector<vector<bool>> visited(rows, vector<bool>(cols, false));
        int count = 0;
        
        for (int i = 0; i < rows; ++i) {
            for (int j = 0; j < cols; ++j) {
                if (A[i][j] == 'X' && !visited[i][j]) {
                    dfs(A, i, j, visited, rows, cols);
                    ++count;
                }
            }
        }
        return count;
    }
    
    void dfs(vector<string> &A, int i, int j, vector<vector<bool>> &visited, int rows, int cols) {
        if (i < 0 || i >= rows || j < 0 || j >= cols || A[i][j] != 'X' || visited[i][j]) {
            return;
        }
        visited[i][j] = true;
        // Explore all four directions
        dfs(A, i + 1, j, visited, rows, cols);
        dfs(A, i - 1, j, visited, rows, cols);
        dfs(A, i, j + 1, visited, rows, cols);
        dfs(A, i, j - 1, visited, rows, cols);
    }
};
```

## Code (Java)

```java
public class Solution {
    public int black(ArrayList<String> A) {
        if (A == null || A.isEmpty()) return 0;
        
        int rows = A.size();
        int cols = A.get(0).length();
        boolean[][] visited = new boolean[rows][cols];
        int count = 0;
        
        for (int i = 0; i < rows; i++) {
            for (int j = 0; j < cols; j++) {
                if (A.get(i).charAt(j) == 'X' && !visited[i][j]) {
                    dfs(A, i, j, visited, rows, cols);
                    count++;
                }
            }
        }
        return count;
    }
    
    private void dfs(ArrayList<String> A, int i, int j, boolean[][] visited, int rows, int cols) {
        if (i < 0 || i >= rows || j < 0 || j >= cols || A.get(i).charAt(j) != 'X' || visited[i][j]) {
            return;
        }
        visited[i][j] = true;
        // Explore all four directions
        dfs(A, i + 1, j, visited, rows, cols);
        dfs(A, i - 1, j, visited, rows, cols);
        dfs(A, i, j + 1, visited, rows, cols);
        dfs(A, i, j - 1, visited, rows, cols);
    }
}
```

## Code (Python)

```python
class Solution:
    def black(self, A):
        if not A:
            return 0
        
        rows = len(A)
        cols = len(A[0]) if rows > 0 else 0
        visited = [[False for _ in range(cols)] for _ in range(rows)]
        count = 0
        
        for i in range(rows):
            for j in range(cols):
                if A[i][j] == 'X' and not visited[i][j]:
                    self.dfs(A, i, j, visited, rows, cols)
                    count += 1
        return count
    
    def dfs(self, A, i, j, visited, rows, cols):
        if i < 0 or i >= rows or j < 0 or j >= cols or A[i][j] != 'X' or visited[i][j]:
            return
        visited[i][j] = True
        # Explore all four directions
        self.dfs(A, i+1, j, visited, rows, cols)
        self.dfs(A, i-1, j, visited, rows, cols)
        self.dfs(A, i, j+1, visited, rows, cols)
        self.dfs(A, i, j-1, visited, rows, cols)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
