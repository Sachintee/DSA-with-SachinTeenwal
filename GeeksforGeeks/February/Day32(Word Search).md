---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Recursion
  - DFS
  - Graph
  - Backtracking
---
# 🚀 _Day 32. Word Search_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/recursion-and-backtracking-gfg-160/problem/word-search)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <string>
using namespace std;

class Solution {
public:
    bool isWordExist(vector<vector<char>>& mat, string word) {
        int n = mat.size();
        int m = mat[0].size();
        
        // DFS function to explore the grid
        function<bool(int, int, int)> dfs = [&](int r, int c, int index) {
            if (index == word.length()) {
                return true;  // Entire word matched
            }
            
            if (r < 0 || r >= n || c < 0 || c >= m || mat[r][c] != word[index]) {
                return false;  // Out of bounds or character mismatch
            }
            
            // Temporarily mark the cell as visited
            char temp = mat[r][c];
            mat[r][c] = '#';
            
            // Explore all four directions
            bool found = (dfs(r + 1, c, index + 1) ||  // Down
                          dfs(r - 1, c, index + 1) ||  // Up
                          dfs(r, c + 1, index + 1) ||  // Right
                          dfs(r, c - 1, index + 1));   // Left
            
            // Restore the cell for backtracking
            mat[r][c] = temp;
            
            return found;
        };
        
        // Iterate through the grid to find the starting letter
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < m; j++) {
                if (mat[i][j] == word[0] && dfs(i, j, 0)) {
                    return true;  // Word found
                }
            }
        }
        
        return false;  // Word not found
    }
};
```

## Code (Java)

```java
class Solution {
    public boolean isWordExist(char[][] mat, String word) {
        int n = mat.length;
        int m = mat[0].length;
        
        // DFS function to explore the grid
        boolean dfs(int r, int c, int index) {
            if (index == word.length()) {
                return true;  // Entire word matched
            }
            
            if (r < 0 || r >= n || c < 0 || c >= m || mat[r][c] != word.charAt(index)) {
                return false;  // Out of bounds or character mismatch
            }
            
            // Temporarily mark the cell as visited
            char temp = mat[r][c];
            mat[r][c] = '#';
            
            // Explore all four directions
            boolean found = (dfs(r + 1, c, index + 1) ||  // Down
                             dfs(r - 1, c, index + 1) ||  // Up
                             dfs(r, c + 1, index + 1) ||  // Right
                             dfs(r, c - 1, index + 1));   // Left
            
            // Restore the cell for backtracking
            mat[r][c] = temp;
            
            return found;
        }
        
        // Iterate through the grid to find the starting letter
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < m; j++) {
                if (mat[i][j] == word.charAt(0) && dfs(i, j, 0)) {
                    return true;  // Word found
                }
            }
        }
        
        return false;  // Word not found
    }
}
```

## Code (Python)

```python

class Solution:
    def isWordExist(self, mat, word):
        n, m = len(mat), len(mat[0])
        
        def dfs(r, c, index):
            if index == len(word):  
                return True  # Successfully matched the entire word
            
            if r < 0 or r >= n or c < 0 or c >= m or mat[r][c] != word[index]:
                return False  # Out of bounds or character mismatch
            
            # Temporarily mark the cell as visited
            temp = mat[r][c]
            mat[r][c] = '#'
            
            # Explore all four possible directions
            found = (dfs(r+1, c, index+1) or  # Down
                     dfs(r-1, c, index+1) or  # Up
                     dfs(r, c+1, index+1) or  # Right
                     dfs(r, c-1, index+1))    # Left
            
            # Restore the cell for backtracking
            mat[r][c] = temp  
            
            return found  

        # Iterate through the grid to find the first letter of the word
        for i in range(n):
            for j in range(m):
                if mat[i][j] == word[0] and dfs(i, j, 0):  
                    return True  # Found the word
        
        return False  # Word not found
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐
