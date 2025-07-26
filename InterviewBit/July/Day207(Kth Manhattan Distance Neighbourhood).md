--- ❤️ ---

# 🚀 _Day 207. Kth Manhattan Distance Neighbourhood_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/kth-manhattan-distance-neighbourhood/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <algorithm>
using namespace std;

class Solution {
public:
    vector<vector<int>> solve(int K, vector<vector<int>> &M) {
        int n = M.size();
        int m = M[0].size();

        vector<vector<int>> prev = M;

        for (int step = 0; step < K; ++step) {
            vector<vector<int>> curr(n, vector<int>(m, 0));

            for (int i = 0; i < n; ++i) {
                for (int j = 0; j < m; ++j) {
                    int max_val = prev[i][j];

                    if (i > 0) max_val = max(max_val, prev[i - 1][j]);
                    if (i < n - 1) max_val = max(max_val, prev[i + 1][j]);
                    if (j > 0) max_val = max(max_val, prev[i][j - 1]);
                    if (j < m - 1) max_val = max(max_val, prev[i][j + 1]);

                    curr[i][j] = max_val;
                }
            }

            prev = curr;
        }

        return prev;
    }
};

```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public int[][] solve(int K, int[][] M) {
        int n = M.length;
        int m = M[0].length;

        int[][] prev = new int[n][m];
        for (int i = 0; i < n; i++)
            prev[i] = Arrays.copyOf(M[i], m);

        for (int step = 0; step < K; step++) {
            int[][] curr = new int[n][m];

            for (int i = 0; i < n; i++) {
                for (int j = 0; j < m; j++) {
                    int maxVal = prev[i][j];

                    if (i > 0) maxVal = Math.max(maxVal, prev[i - 1][j]);
                    if (i < n - 1) maxVal = Math.max(maxVal, prev[i + 1][j]);
                    if (j > 0) maxVal = Math.max(maxVal, prev[i][j - 1]);
                    if (j < m - 1) maxVal = Math.max(maxVal, prev[i][j + 1]);

                    curr[i][j] = maxVal;
                }
            }

            prev = curr;
        }

        return prev;
    }
}

```

## Code (Python)

```python
class Solution:
    def solve(self, K, M):
        n = len(M)
        m = len(M[0])

        prev = [row[:] for row in M]  # Initialize with original matrix

        for step in range(K):
            curr = [[0] * m for _ in range(n)]
            for i in range(n):
                for j in range(m):
                    # Start with current value
                    max_val = prev[i][j]

                    # Check 4 neighbors within 1 Manhattan step
                    for dx, dy in [(-1, 0), (1, 0), (0, -1), (0, 1)]:
                        ni, nj = i + dx, j + dy
                        if 0 <= ni < n and 0 <= nj < m:
                            max_val = max(max_val, prev[ni][nj])

                    curr[i][j] = max_val

            prev = curr  # Move to next step

        return prev

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
