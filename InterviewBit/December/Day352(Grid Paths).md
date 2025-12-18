--- ❤️ ---

# 🚀 _Day 352. Grid Paths_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/grid-paths/)

## 🎯 **My Approach:**


## Code(C++)
```cpp

```

## Code (Java)

```java

```

## Code (Python)

```python
class Solution {
public:
    int N;
    int totalCells;
    long long ans = 0;
    vector<vector<int>> grid;
    vector<vector<bool>> visited;
    int dx[4] = {1, -1, 0, 0};
    int dy[4] = {0, 0, 1, -1};

    void dfs(int x, int y, int visitedCount, long long cost, int prevVal) {
        // If reached destination
        if (x == N - 1 && y == N - 1) {
            if (visitedCount == totalCells) {
                ans += cost;
            }
            return;
        }

        for (int d = 0; d < 4; d++) {
            int nx = x + dx[d];
            int ny = y + dy[d];

            if (nx >= 0 && nx < N && ny >= 0 && ny < N) {
                if (!visited[nx][ny] && grid[nx][ny] != 0) {
                    visited[nx][ny] = true;
                    dfs(
                        nx, ny,
                        visitedCount + 1,
                        cost + abs(grid[nx][ny] - prevVal),
                        grid[nx][ny]
                    );
                    visited[nx][ny] = false;
                }
            }
        }
    }

    int solve(vector<vector<int>> &A) {
        grid = A;
        N = grid.size();
        visited.assign(N, vector<bool>(N, false));

        // Count unblocked cells
        totalCells = 0;
        for (int i = 0; i < N; i++) {
            for (int j = 0; j < N; j++) {
                if (grid[i][j] != 0)
                    totalCells++;
            }
        }

        // Start DFS from (0,0)
        visited[0][0] = true;
        dfs(0, 0, 1, 0, grid[0][0]);

        return ans;
    }
};

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
