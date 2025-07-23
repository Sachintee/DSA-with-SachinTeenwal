--- ❤️ ---

# 🚀 _Day 204. Longest Arithmetic Progression_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/longest-arithmetic-progression/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <unordered_map>
#include <algorithm>
using namespace std;

class Solution {
public:
    int solve(vector<int> &A) {
        int n = A.size();
        if (n <= 2) return n;

        vector<unordered_map<long long, int>> dp(n);
        int max_len = 2;

        for (int i = 0; i < n; i++) {
            for (int j = 0; j < i; j++) {
                long long diff = (long long)A[i] - A[j];
                if (dp[j].count(diff)) {
                    dp[i][diff] = dp[j][diff] + 1;
                } else {
                    dp[i][diff] = 2;
                }
                max_len = max(max_len, dp[i][diff]);
            }
        }

        return max_len;
    }
};

```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public int solve(int[] A) {
        int n = A.length;
        if (n <= 2) return n;

        Map<Integer, Integer>[] dp = new HashMap[n];
        for (int i = 0; i < n; i++) {
            dp[i] = new HashMap<>();
        }

        int max_len = 2;

        for (int i = 0; i < n; i++) {
            for (int j = 0; j < i; j++) {
                long diff = (long)A[i] - A[j];
                int d = (int)diff; // safe as constraints are within integer

                int len = dp[j].getOrDefault(d, 1) + 1;
                dp[i].put(d, len);
                max_len = Math.max(max_len, len);
            }
        }

        return max_len;
    }
}

```

## Code (Python)

```python
class Solution:
    # @param A : tuple of integers
    # @return an integer
    def solve(self, A):
        n = len(A)
        if n <= 2:
            return n

        dp = [{} for _ in range(n)]
        max_len = 2

        for i in range(n):
            for j in range(i):
                diff = A[i] - A[j]
                if diff in dp[j]:
                    dp[i][diff] = dp[j][diff] + 1
                else:
                    dp[i][diff] = 2
                max_len = max(max_len, dp[i][diff])

        return max_len

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
