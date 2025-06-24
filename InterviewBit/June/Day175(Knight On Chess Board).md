--- ❤️ ---

# 🚀 _Day 175. Knight On Chess Board_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/knight-on-chess-board/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <vector>
#include <queue>
using namespace std;

class Solution {
public:
    int knight(int A, int B, int C, int D, int E, int F) {
        vector<pair<int, int>> directions = {
            {-2, -1}, {-2, 1}, {-1, -2}, {-1, 2},
            {1, -2}, {1, 2}, {2, -1}, {2, 1}
        };

        int start_x = C - 1, start_y = D - 1;
        int end_x = E - 1, end_y = F - 1;

        if (start_x == end_x && start_y == end_y)
            return 0;

        vector<vector<bool>> visited(A, vector<bool>(B, false));
        queue<tuple<int, int, int>> q;
        q.push({start_x, start_y, 0});
        visited[start_x][start_y] = true;

        while (!q.empty()) {
            auto [x, y, steps] = q.front();
            q.pop();

            for (auto [dx, dy] : directions) {
                int nx = x + dx;
                int ny = y + dy;

                if (nx >= 0 && nx < A && ny >= 0 && ny < B && !visited[nx][ny]) {
                    if (nx == end_x && ny == end_y)
                        return steps + 1;

                    visited[nx][ny] = true;
                    q.push({nx, ny, steps + 1});
                }
            }
        }
        return -1;
    }
};

```

## Code (Java)

```java
import java.util.*;

class Solution {
    public int knight(int A, int B, int C, int D, int E, int F) {
        int[][] directions = {
            {-2, -1}, {-2, 1}, {-1, -2}, {-1, 2},
            {1, -2}, {1, 2}, {2, -1}, {2, 1}
        };

        int startX = C - 1, startY = D - 1;
        int endX = E - 1, endY = F - 1;

        if (startX == endX && startY == endY)
            return 0;

        boolean[][] visited = new boolean[A][B];
        Queue<int[]> queue = new LinkedList<>();
        queue.offer(new int[]{startX, startY, 0});
        visited[startX][startY] = true;

        while (!queue.isEmpty()) {
            int[] curr = queue.poll();
            int x = curr[0], y = curr[1], steps = curr[2];

            for (int[] dir : directions) {
                int nx = x + dir[0];
                int ny = y + dir[1];

                if (nx >= 0 && nx < A && ny >= 0 && ny < B && !visited[nx][ny]) {
                    if (nx == endX && ny == endY)
                        return steps + 1;

                    visited[nx][ny] = true;
                    queue.offer(new int[]{nx, ny, steps + 1});
                }
            }
        }
        return -1;
    }
}

```

## Code (Python)

```python
from collections import deque

class Solution:
    def knight(self, A, B, C, D, E, F):
        # Directions the knight can move (8 possible moves)
        directions = [(-2, -1), (-2, 1), (-1, -2), (-1, 2),
                      (1, -2), (1, 2), (2, -1), (2, 1)]
        
        # Convert to 0-based or keep as 1-based based on problem statement
        # Assuming positions are 1-based as per the example
        start_x, start_y = C - 1, D - 1  # converting to 0-based for easier handling
        end_x, end_y = E - 1, F - 1
        
        if start_x == end_x and start_y == end_y:
            return 0
        
        visited = [[False for _ in range(B)] for _ in range(A)]
        queue = deque()
        queue.append((start_x, start_y, 0))
        visited[start_x][start_y] = True
        
        while queue:
            x, y, steps = queue.popleft()
            for dx, dy in directions:
                nx = x + dx
                ny = y + dy
                if 0 <= nx < A and 0 <= ny < B and not visited[nx][ny]:
                    if nx == end_x and ny == end_y:
                        return steps + 1
                    visited[nx][ny] = True
                    queue.append((nx, ny, steps + 1))
        return -1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
