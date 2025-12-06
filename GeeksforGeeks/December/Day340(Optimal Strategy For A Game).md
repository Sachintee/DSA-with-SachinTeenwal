--- ❤️ ---

# 🚀 _Day 340. Optimal Strategy For A Game_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/optimal-strategy-for-a-game-1587115620/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int maximumAmount(vector<int> &arr) {
        int n = arr.size();
        vector<vector<long long>> dp(n, vector<long long>(n, 0));

        for (int i = 0; i < n; i++) dp[i][i] = arr[i];

        for (int len = 2; len <= n; len++) {
            for (int i = 0; i + len - 1 < n; i++) {
                int j = i + len - 1;

                long long a = (i + 2 <= j) ? dp[i + 2][j] : 0;
                long long b = (i + 1 <= j - 1) ? dp[i + 1][j - 1] : 0;
                long long c = (i <= j - 2) ? dp[i][j - 2] : 0;

                dp[i][j] = max(
                    arr[i] + min(a, b),
                    arr[j] + min(b, c)
                );
            }
        }

        return dp[0][n - 1];
    }
};

```

## Code (Java)

```java

```

## Code (Python)

```python

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
