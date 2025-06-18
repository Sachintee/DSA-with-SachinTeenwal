--- ❤️ ---

# 🚀 _Day 169. Water Flow_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/water-flow/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <queue>
#include <utility>
using namespace std;

class Solution {
public:
    int solve(vector<vector<int>>& A) {
        if (A.empty() || A[0].empty()) return 0;
        
        int rows = A.size();
        int cols = A[0].size();
        vector<vector<bool>> blue_reachable(rows, vector<bool>(cols, false));
        vector<vector<bool>> red_reachable(rows, vector<bool>(cols, false));
        
        // Directions: up, down, left, right
        vector<pair<int, int>> directions = {{-1, 0}, {1, 0}, {0, -1}, {0, 1}};
        
        // BFS for Blue lake (left and top edges)
        queue<pair<int, int>> q;
        
        // Add left edge
        for (int i = 0; i < rows; ++i) {
            q.push({i, 0});
            blue_reachable[i][0] = true;
        }
        
        // Add top edge (excluding (0,0) to avoid duplication)
        for (int j = 1; j < cols; ++j) {
            q.push({0, j});
            blue_reachable[0][j] = true;
        }
        
        while (!q.empty()) {
            auto [x, y] = q.front();
            q.pop();
            for (auto [dx, dy] : directions) {
                int nx = x + dx;
                int ny = y + dy;
                if (nx >= 0 && nx < rows && ny >= 0 && ny < cols) {
                    if (!blue_reachable[nx][ny] && A[nx][ny] >= A[x][y]) {
                        blue_reachable[nx][ny] = true;
                        q.push({nx, ny});
                    }
                }
            }
        }
        
        // BFS for Red lake (right and bottom edges)
        q = queue<pair<int, int>>();
        
        // Add right edge
        for (int i = 0; i < rows; ++i) {
            q.push({i, cols - 1});
            red_reachable[i][cols - 1] = true;
        }
        
        // Add bottom edge (excluding (rows-1, cols-1) to avoid duplication)
        for (int j = 0; j < cols - 1; ++j) {
            q.push({rows - 1, j});
            red_reachable[rows - 1][j] = true;
        }
        
        while (!q.empty()) {
            auto [x, y] = q.front();
            q.pop();
            for (auto [dx, dy] : directions) {
                int nx = x + dx;
                int ny = y + dy;
                if (nx >= 0 && nx < rows && ny >= 0 && ny < cols) {
                    if (!red_reachable[nx][ny] && A[nx][ny] >= A[x][y]) {
                        red_reachable[nx][ny] = true;
                        q.push({nx, ny});
                    }
                }
            }
        }
        
        // Count cells reachable by both
        int count = 0;
        for (int i = 0; i < rows; ++i) {
            for (int j = 0; j < cols; ++j) {
                if (blue_reachable[i][j] && red_reachable[i][j]) {
                    ++count;
                }
            }
        }
        
        return count;
    }
};
```

## Code (Java)

```java
import java.util.*;

class Solution {
    public int solve(int[][] A) {
        if (A == null || A.length == 0 || A[0].length == 0) return 0;
        
        int rows = A.length;
        int cols = A[0].length;
        boolean[][] blueReachable = new boolean[rows][cols];
        boolean[][] redReachable = new boolean[rows][cols];
        
        // Directions: up, down, left, right
        int[][] directions = {{-1, 0}, {1, 0}, {0, -1}, {0, 1}};
        
        // BFS for Blue lake (left and top edges)
        Queue<int[]> queue = new LinkedList<>();
        
        // Add left edge
        for (int i = 0; i < rows; i++) {
            queue.offer(new int[]{i, 0});
            blueReachable[i][0] = true;
        }
        
        // Add top edge (excluding (0,0) to avoid duplication)
        for (int j = 1; j < cols; j++) {
            queue.offer(new int[]{0, j});
            blueReachable[0][j] = true;
        }
        
        while (!queue.isEmpty()) {
            int[] current = queue.poll();
            int x = current[0];
            int y = current[1];
            for (int[] dir : directions) {
                int nx = x + dir[0];
                int ny = y + dir[1];
                if (nx >= 0 && nx < rows && ny >= 0 && ny < cols) {
                    if (!blueReachable[nx][ny] && A[nx][ny] >= A[x][y]) {
                        blueReachable[nx][ny] = true;
                        queue.offer(new int[]{nx, ny});
                    }
                }
            }
        }
        
        // BFS for Red lake (right and bottom edges)
        queue = new LinkedList<>();
        
        // Add right edge
        for (int i = 0; i < rows; i++) {
            queue.offer(new int[]{i, cols - 1});
            redReachable[i][cols - 1] = true;
        }
        
        // Add bottom edge (excluding (rows-1, cols-1) to avoid duplication)
        for (int j = 0; j < cols - 1; j++) {
            queue.offer(new int[]{rows - 1, j});
            redReachable[rows - 1][j] = true;
        }
        
        while (!queue.isEmpty()) {
            int[] current = queue.poll();
            int x = current[0];
            int y = current[1];
            for (int[] dir : directions) {
                int nx = x + dir[0];
                int ny = y + dir[1];
                if (nx >= 0 && nx < rows && ny >= 0 && ny < cols) {
                    if (!redReachable[nx][ny] && A[nx][ny] >= A[x][y]) {
                        redReachable[nx][ny] = true;
                        queue.offer(new int[]{nx, ny});
                    }
                }
            }
        }
        
        // Count cells reachable by both
        int count = 0;
        for (int i = 0; i < rows; i++) {
            for (int j = 0; j < cols; j++) {
                if (blueReachable[i][j] && redReachable[i][j]) {
                    count++;
                }
            }
        }
        
        return count;
    }
}
```

## Code (Python)

```python
from collections import deque

class Solution:
    def solve(self, A):
        if not A or not A[0]:
            return 0
        
        rows, cols = len(A), len(A[0])
        blue_reachable = [[False for _ in range(cols)] for _ in range(rows)]
        red_reachable = [[False for _ in range(cols)] for _ in range(rows)]
        
        # Directions: up, down, left, right
        directions = [(-1, 0), (1, 0), (0, -1), (0, 1)]
        
        # BFS for Blue lake (left and top edges)
        queue = deque()
        
        # Add left edge
        for i in range(rows):
            queue.append((i, 0))
            blue_reachable[i][0] = True
        
        # Add top edge (excluding (0,0) to avoid duplication)
        for j in range(1, cols):
            queue.append((0, j))
            blue_reachable[0][j] = True
        
        while queue:
            x, y = queue.popleft()
            for dx, dy in directions:
                nx, ny = x + dx, y + dy
                if 0 <= nx < rows and 0 <= ny < cols:
                    if not blue_reachable[nx][ny] and A[nx][ny] >= A[x][y]:
                        blue_reachable[nx][ny] = True
                        queue.append((nx, ny))
        
        # BFS for Red lake (right and bottom edges)
        queue = deque()
        
        # Add right edge
        for i in range(rows):
            queue.append((i, cols - 1))
            red_reachable[i][cols - 1] = True
        
        # Add bottom edge (excluding (rows-1, cols-1) to avoid duplication)
        for j in range(cols - 1):
            queue.append((rows - 1, j))
            red_reachable[rows - 1][j] = True
        
        while queue:
            x, y = queue.popleft()
            for dx, dy in directions:
                nx, ny = x + dx, y + dy
                if 0 <= nx < rows and 0 <= ny < cols:
                    if not red_reachable[nx][ny] and A[nx][ny] >= A[x][y]:
                        red_reachable[nx][ny] = True
                        queue.append((nx, ny))
        
        # Count cells reachable by both
        count = 0
        for i in range(rows):
            for j in range(cols):
                if blue_reachable[i][j] and red_reachable[i][j]:
                    count += 1
        
        return count
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
