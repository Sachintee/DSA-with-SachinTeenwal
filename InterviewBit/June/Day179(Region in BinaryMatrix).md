--- ❤️ ---

# 🚀 _Day 179. Region in BinaryMatrix_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/region-in-binarymatrix/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <stack>
#include <algorithm>

using namespace std;

class Solution {
public:
    int solve(vector<vector<int>>& A) {
        if (A.empty() || A[0].empty()) {
            return 0;
        }
        
        int rows = A.size();
        int cols = A[0].size();
        int max_region = 0;
        
        for (int i = 0; i < rows; ++i) {
            for (int j = 0; j < cols; ++j) {
                if (A[i][j] == 1) {
                    stack<pair<int, int>> stk;
                    stk.push({i, j});
                    A[i][j] = 0; // Mark as visited
                    int current_region = 0;
                    
                    while (!stk.empty()) {
                        auto [x, y] = stk.top();
                        stk.pop();
                        current_region++;
                        
                        // Check all 8 possible neighbors
                        for (int dx = -1; dx <= 1; ++dx) {
                            for (int dy = -1; dy <= 1; ++dy) {
                                if (dx == 0 && dy == 0) {
                                    continue; // Skip the current cell
                                }
                                int nx = x + dx;
                                int ny = y + dy;
                                if (nx >= 0 && nx < rows && ny >= 0 && ny < cols && A[nx][ny] == 1) {
                                    A[nx][ny] = 0; // Mark as visited
                                    stk.push({nx, ny});
                                }
                            }
                        }
                    }
                    
                    max_region = max(max_region, current_region);
                }
            }
        }
        
        return max_region;
    }
};
```

## Code (Java)

```java
import java.util.Stack;

public class Solution {
    public int solve(int[][] A) {
        if (A == null || A.length == 0 || A[0].length == 0) {
            return 0;
        }
        
        int rows = A.length;
        int cols = A[0].length;
        int maxRegion = 0;
        
        for (int i = 0; i < rows; i++) {
            for (int j = 0; j < cols; j++) {
                if (A[i][j] == 1) {
                    Stack<int[]> stack = new Stack<>();
                    stack.push(new int[]{i, j});
                    A[i][j] = 0; // Mark as visited
                    int currentRegion = 0;
                    
                    while (!stack.isEmpty()) {
                        int[] cell = stack.pop();
                        int x = cell[0];
                        int y = cell[1];
                        currentRegion++;
                        
                        // Check all 8 possible neighbors
                        for (int dx = -1; dx <= 1; dx++) {
                            for (int dy = -1; dy <= 1; dy++) {
                                if (dx == 0 && dy == 0) {
                                    continue; // Skip the current cell
                                }
                                int nx = x + dx;
                                int ny = y + dy;
                                if (nx >= 0 && nx < rows && ny >= 0 && ny < cols && A[nx][ny] == 1) {
                                    A[nx][ny] = 0; // Mark as visited
                                    stack.push(new int[]{nx, ny});
                                }
                            }
                        }
                    }
                    
                    maxRegion = Math.max(maxRegion, currentRegion);
                }
            }
        }
        
        return maxRegion;
    }
}
```

## Code (Python)

```python
class Solution:
    def solve(self, A):
        if not A or not A[0]:
            return 0
        
        rows = len(A)
        cols = len(A[0])
        max_region = 0
        
        for i in range(rows):
            for j in range(cols):
                if A[i][j] == 1:
                    stack = [(i, j)]
                    A[i][j] = 0  # Mark as visited
                    current_region = 0
                    
                    while stack:
                        x, y = stack.pop()
                        current_region += 1
                        
                        # Check all 8 possible neighbors
                        for dx in [-1, 0, 1]:
                            for dy in [-1, 0, 1]:
                                if dx == 0 and dy == 0:
                                    continue  # Skip the current cell
                                nx, ny = x + dx, y + dy
                                if 0 <= nx < rows and 0 <= ny < cols and A[nx][ny] == 1:
                                    A[nx][ny] = 0  # Mark as visited
                                    stack.append((nx, ny))
                    
                    max_region = max(max_region, current_region)
        
        return max_region
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
