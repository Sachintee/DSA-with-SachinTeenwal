--- ❤️ ---

# 🚀 _Day 57. Maximum Sum Square SubMatrix_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/maximum-sum-square-submatrix/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <algorithm>
#include <climits>

using namespace std;

int Solution::solve(vector<vector<int>> &A, int B) {
    int n = A.size();
    // Create a prefix sum matrix
    vector<vector<int>> prefix(n + 1, vector<int>(n + 1, 0));
    
    // Fill the prefix sum matrix
    for (int i = 1; i <= n; i++) {
        int row_sum = 0;
        for (int j = 1; j <= n; j++) {
            row_sum += A[i - 1][j - 1];
            prefix[i][j] = prefix[i - 1][j] + row_sum;
        }
    }
    
    int max_sum = INT_MIN;
    
    // Calculate the sum of each B x B submatrix using the prefix sum matrix
    for (int i = B; i <= n; i++) {
        for (int j = B; j <= n; j++) {
            int total = prefix[i][j] - prefix[i - B][j] - prefix[i][j - B] + prefix[i - B][j - B];
            if (total > max_sum) {
                max_sum = total;
            }
        }
    }
    
    return max_sum;
}
```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public int solve(int[][] A, int B) {
        int n = A.length;
        // Create a prefix sum matrix
        int[][] prefix = new int[n + 1][n + 1];
        
        // Fill the prefix sum matrix
        for (int i = 1; i <= n; i++) {
            int row_sum = 0;
            for (int j = 1; j <= n; j++) {
                row_sum += A[i - 1][j - 1];
                prefix[i][j] = prefix[i - 1][j] + row_sum;
            }
        }
        
        int max_sum = Integer.MIN_VALUE;
        
        // Calculate the sum of each B x B submatrix using the prefix sum matrix
        for (int i = B; i <= n; i++) {
            for (int j = B; j <= n; j++) {
                int total = prefix[i][j] - prefix[i - B][j] - prefix[i][j - B] + prefix[i - B][j - B];
                if (total > max_sum) {
                    max_sum = total;
                }
            }
        }
        
        return max_sum;
    }
}
```

## Code (Python)

```python
class Solution:
    def solve(self, A, B):
        n = len(A)
        # Create a prefix sum matrix
        prefix = [[0] * (n + 1) for _ in range(n + 1)]
        
        # Fill the prefix sum matrix
        for i in range(1, n + 1):
            row_sum = 0
            for j in range(1, n + 1):
                row_sum += A[i - 1][j - 1]
                prefix[i][j] = prefix[i - 1][j] + row_sum
        
        max_sum = float('-inf')
        
        # Calculate the sum of each B x B submatrix using the prefix sum matrix
        for i in range(B, n + 1):
            for j in range(B, n + 1):
                total = prefix[i][j] - prefix[i - B][j] - prefix[i][j - B] + prefix[i - B][j - B]
                if total > max_sum:
                    max_sum = total
        
        return max_sum
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
