--- ❤️ ---

# 🚀 _Day 311. Diagonally powerful Matrix_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/diagonally-powerful-matrix/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <cmath>
#include <climits>
#include <algorithm>
using namespace std;

class Solution {
public:
    int solve(vector<vector<int>>& A) {
        int rows = A.size();
        int cols = A[0].size();
        vector<vector<int>> diagonals;
        
        // Diagonals starting from top row
        for (int c = 0; c < cols; c++) {
            vector<int> diag;
            int r = 0;
            int cc = c;
            while (r < rows && cc < cols) {
                diag.push_back(A[r][cc]);
                r++;
                cc++;
            }
            diagonals.push_back(diag);
        }
        
        // Diagonals starting from left column (skip first to avoid duplicate)
        for (int r = 1; r < rows; r++) {
            vector<int> diag;
            int rr = r;
            int c = 0;
            while (rr < rows && c < cols) {
                diag.push_back(A[rr][c]);
                rr++;
                c++;
            }
            diagonals.push_back(diag);
        }
        
        int total_ops = 0;
        const int max_bit = 24; // since 1e7 < 2^24
        
        for (auto& diag : diagonals) {
            int min_cost = INT_MAX;
            for (int k = 1; k < max_bit; k++) {
                int cost = 0;
                for (int x : diag) {
                    int min_shift = INT_MAX;
                    // find all set bits in x
                    for (int j = 0; j < max_bit; j++) {
                        if (x & (1 << j)) {
                            min_shift = min(min_shift, abs(j - k));
                        }
                    }
                    cost += min_shift;
                }
                min_cost = min(min_cost, cost);
            }
            total_ops += min_cost;
        }
        
        return total_ops;
    }
};
```

## Code (Java)

```java
import java.util.*;

class Solution {
    public int solve(int[][] A) {
        int rows = A.length;
        int cols = A[0].length;
        List<List<Integer>> diagonals = new ArrayList<>();
        
        // Diagonals starting from top row
        for (int c = 0; c < cols; c++) {
            List<Integer> diag = new ArrayList<>();
            int r = 0;
            int cc = c;
            while (r < rows && cc < cols) {
                diag.add(A[r][cc]);
                r++;
                cc++;
            }
            diagonals.add(diag);
        }
        
        // Diagonals starting from left column (skip first to avoid duplicate)
        for (int r = 1; r < rows; r++) {
            List<Integer> diag = new ArrayList<>();
            int rr = r;
            int c = 0;
            while (rr < rows && c < cols) {
                diag.add(A[rr][c]);
                rr++;
                c++;
            }
            diagonals.add(diag);
        }
        
        int totalOps = 0;
        final int maxBit = 24; // since 1e7 < 2^24
        
        for (List<Integer> diag : diagonals) {
            int minCost = Integer.MAX_VALUE;
            for (int k = 1; k < maxBit; k++) {
                int cost = 0;
                for (int x : diag) {
                    int minShift = Integer.MAX_VALUE;
                    // find all set bits in x
                    for (int j = 0; j < maxBit; j++) {
                        if ((x & (1 << j)) != 0) {
                            minShift = Math.min(minShift, Math.abs(j - k));
                        }
                    }
                    cost += minShift;
                }
                minCost = Math.min(minCost, cost);
            }
            totalOps += minCost;
        }
        
        return totalOps;
    }
}
```

## Code (Python)

```python
class Solution:
    def solve(self, A):
        rows, cols = len(A), len(A[0])
        diagonals = []
        
        # Diagonals starting from top row
        for c in range(cols):
            diag = []
            r = 0
            cc = c
            while r < rows and cc < cols:
                diag.append(A[r][cc])
                r += 1
                cc += 1
            diagonals.append(diag)
        
        # Diagonals starting from left column (skip first to avoid duplicate with (0,0))
        for r in range(1, rows):
            diag = []
            rr = r
            c = 0
            while rr < rows and c < cols:
                diag.append(A[rr][c])
                rr += 1
                c += 1
            diagonals.append(diag)
        
        total_ops = 0
        max_bit = 24  # since 1e7 < 2^24
        
        for diag in diagonals:
            min_cost = float('inf')
            for k in range(1, max_bit):  # k >= 1
                cost = 0
                for x in diag:
                    min_shift = float('inf')
                    # find all set bits in x
                    for j in range(max_bit):
                        if x >> j & 1:
                            min_shift = min(min_shift, abs(j - k))
                    cost += min_shift
                min_cost = min(min_cost, cost)
            total_ops += min_cost
        
        return total_ops
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
