--- ❤️ ---

# 🚀 _Day 222. Egg Drop Problem!_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/egg-drop-problem/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <bits/stdc++.h>
using namespace std;

class Solution {
public:
    int solve(int A, int B) {
        vector<vector<int>> dp(A + 1, vector<int>(B + 1, 0));

        // Base cases:
        // With 1 egg, need 'B' trials (drop from each floor)
        for (int j = 1; j <= B; j++)
            dp[1][j] = j;

        // With 0 floors, 0 trials; with 1 floor, 1 trial
        for (int i = 1; i <= A; i++) {
            dp[i][0] = 0;
            dp[i][1] = 1;
        }

        for (int eggs = 2; eggs <= A; eggs++) {
            for (int floors = 2; floors <= B; floors++) {
                int low = 1, high = floors, res = floors;
                while (low <= high) {
                    int mid = (low + high) / 2;
                    int breakCase = dp[eggs - 1][mid - 1]; // Egg breaks
                    int notBreakCase = dp[eggs][floors - mid]; // Egg doesn't break
                    int worst = 1 + max(breakCase, notBreakCase);

                    if (breakCase > notBreakCase) {
                        high = mid - 1;
                        res = min(res, worst);
                    } else {
                        low = mid + 1;
                        res = min(res, worst);
                    }
                }
                dp[eggs][floors] = res;
            }
        }
        return dp[A][B];
    }
};

int main() {
    Solution s;
    cout << s.solve(2, 10) << endl; // Output: 4
    return 0;
}

```

## Code (Java)

```java
class Solution {
    public int solve(int A, int B) {
        int[][] dp = new int[A + 1][B + 1];

        // Base cases:
        // With 1 egg, need 'B' trials (drop from each floor)
        for (int j = 1; j <= B; j++)
            dp[1][j] = j;

        // With 0 floors, 0 trials; with 1 floor, 1 trial
        for (int i = 1; i <= A; i++) {
            dp[i][0] = 0;
            dp[i][1] = 1;
        }

        for (int eggs = 2; eggs <= A; eggs++) {
            for (int floors = 2; floors <= B; floors++) {
                int low = 1, high = floors, res = floors;
                while (low <= high) {
                    int mid = (low + high) / 2;
                    int breakCase = dp[eggs - 1][mid - 1]; // Egg breaks
                    int notBreakCase = dp[eggs][floors - mid]; // Egg doesn't break
                    int worst = 1 + Math.max(breakCase, notBreakCase);

                    if (breakCase > notBreakCase) {
                        high = mid - 1;
                        res = Math.min(res, worst);
                    } else {
                        low = mid + 1;
                        res = Math.min(res, worst);
                    }
                }
                dp[eggs][floors] = res;
            }
        }
        return dp[A][B];
    }

    public static void main(String[] args) {
        Solution s = new Solution();
        System.out.println(s.solve(2, 10)); // Output: 4
    }
}

```

## Code (Python)

```python
class Solution:
    def solve(self, A, B):
        # dp[a] = maximum floors we can check with 'a' eggs
        dp = [0] * (A + 1)
        moves = 0

        while dp[A] < B:
            moves += 1
            for eggs in range(A, 0, -1):
                dp[eggs] = dp[eggs] + dp[eggs - 1] + 1
        return moves

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
