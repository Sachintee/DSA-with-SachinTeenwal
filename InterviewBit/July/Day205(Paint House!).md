--- ❤️ ---

# 🚀 _Day 205. Paint House!_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/paint-house/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <algorithm>
using namespace std;

class Solution {
public:
    int solve(vector<vector<int>> &A) {
        int n = A.size();
        if (n == 0) return 0;

        vector<int> dp = A[0]; // cost for first house

        for (int i = 1; i < n; i++) {
            vector<int> prev = dp;
            dp[0] = A[i][0] + min(prev[1], prev[2]);
            dp[1] = A[i][1] + min(prev[0], prev[2]);
            dp[2] = A[i][2] + min(prev[0], prev[1]);
        }

        return min({dp[0], dp[1], dp[2]});
    }
};

```

## Code (Java)

```java
public class Solution {
    public int solve(int[][] A) {
        int n = A.length;
        if (n == 0) return 0;

        int[] dp = new int[3];
        dp[0] = A[0][0];
        dp[1] = A[0][1];
        dp[2] = A[0][2];

        for (int i = 1; i < n; i++) {
            int[] prev = dp.clone();
            dp[0] = A[i][0] + Math.min(prev[1], prev[2]);
            dp[1] = A[i][1] + Math.min(prev[0], prev[2]);
            dp[2] = A[i][2] + Math.min(prev[0], prev[1]);
        }

        return Math.min(dp[0], Math.min(dp[1], dp[2]));
    }
}

```

## Code (Python)

```python
class Solution:
    def solve(self, A):
        n = len(A)
        if n == 0:
            return 0

        dp = A[0][:]  # cost for first house

        for i in range(1, n):
            prev = dp[:]
            dp[0] = A[i][0] + min(prev[1], prev[2])
            dp[1] = A[i][1] + min(prev[0], prev[2])
            dp[2] = A[i][2] + min(prev[0], prev[1])

        return min(dp)

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
