--- ❤️ ---

# 🚀 _Day 153. Hotel Service_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/hotel-service/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <queue>
#include <climits>
using namespace std;

class Solution {
public:
    vector<int> nearestHotel(vector<vector<int>>& A, vector<vector<int>>& B) {
        int N = A.size();
        int M = A[0].size();
        vector<vector<int>> distance(N, vector<int>(M, INT_MAX));
        queue<pair<int, int>> q;

        // Directions: up, down, left, right
        int dx[] = {-1, 1, 0, 0};
        int dy[] = {0, 0, -1, 1};

        // Enqueue all hotel positions
        for (int i = 0; i < N; ++i) {
            for (int j = 0; j < M; ++j) {
                if (A[i][j] == 1) {
                    distance[i][j] = 0;
                    q.push({i, j});
                }
            }
        }

        // BFS to fill the distance matrix
        while (!q.empty()) {
            auto [x, y] = q.front();
            q.pop();
            for (int dir = 0; dir < 4; ++dir) {
                int nx = x + dx[dir], ny = y + dy[dir];
                if (nx >= 0 && ny >= 0 && nx < N && ny < M) {
                    if (distance[nx][ny] > distance[x][y] + 1) {
                        distance[nx][ny] = distance[x][y] + 1;
                        q.push({nx, ny});
                    }
                }
            }
        }

        // Answer queries
        vector<int> result;
        for (auto& coord : B) {
            int x = coord[0] - 1, y = coord[1] - 1;
            result.push_back(distance[x][y]);
        }

        return result;
    }
};

```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public List<Integer> nearestHotel(int[][] A, int[][] B) {
        int N = A.length;
        int M = A[0].length;
        int[][] distance = new int[N][M];
        for (int[] row : distance)
            Arrays.fill(row, Integer.MAX_VALUE);
        
        Queue<int[]> q = new LinkedList<>();
        
        // Directions: up, down, left, right
        int[] dx = {-1, 1, 0, 0};
        int[] dy = {0, 0, -1, 1};

        // Enqueue all hotel positions
        for (int i = 0; i < N; i++) {
            for (int j = 0; j < M; j++) {
                if (A[i][j] == 1) {
                    distance[i][j] = 0;
                    q.add(new int[]{i, j});
                }
            }
        }

        // BFS to fill the distance matrix
        while (!q.isEmpty()) {
            int[] pos = q.poll();
            int x = pos[0], y = pos[1];
            for (int dir = 0; dir < 4; dir++) {
                int nx = x + dx[dir], ny = y + dy[dir];
                if (nx >= 0 && ny >= 0 && nx < N && ny < M) {
                    if (distance[nx][ny] > distance[x][y] + 1) {
                        distance[nx][ny] = distance[x][y] + 1;
                        q.add(new int[]{nx, ny});
                    }
                }
            }
        }

        // Answer queries
        List<Integer> result = new ArrayList<>();
        for (int[] coord : B) {
            int x = coord[0] - 1, y = coord[1] - 1;
            result.add(distance[x][y]);
        }

        return result;
    }
}

```

## Code (Python)

```python
from collections import deque

class Solution:
    # @param A : list of list of integers
    # @param B : list of list of integers
    # @return a list of integers
    def nearestHotel(self, A, B):
        if not A or not A[0]:
            return []
        
        N = len(A)
        M = len(A[0])
        
        # Initialize distance matrix with infinity
        distance = [[float('inf')] * M for _ in range(N)]
        q = deque()
        
        # Directions for moving in 4 possible adjacent cells
        directions = [(-1, 0), (1, 0), (0, -1), (0, 1)]
        
        # Enqueue all hotel cells (1s) with distance 0
        for i in range(N):
            for j in range(M):
                if A[i][j] == 1:
                    distance[i][j] = 0
                    q.append((i, j))
        
        # Perform BFS to fill the distance matrix
        while q:
            x, y = q.popleft()
            for dx, dy in directions:
                nx, ny = x + dx, y + dy
                if 0 <= nx < N and 0 <= ny < M:
                    if distance[nx][ny] > distance[x][y] + 1:
                        distance[nx][ny] = distance[x][y] + 1
                        q.append((nx, ny))
        
        # Process each query in B
        result = []
        for coord in B:
            x, y = coord[0] - 1, coord[1] - 1  # Convert to 0-based index
            result.append(distance[x][y])
        
        return result
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
