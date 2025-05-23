# *143. Dice throw*

The problem can be found at the following link: 🔗 **[Question Link](https://www.geeksforgeeks.org/problems/dice-throw5349/1)**


## **🧩 Problem Description**

Given `n` dice, each having faces numbered from `1` to `m`, find the number of ways to get a total sum `x` when all the dice are thrown.

You must count every distinct sequence of face-up values (order matters).

You are given:

* `n` dice,
* each having `m` faces numbered from 1 to `m`,
* and a target sum `x`.

Find the number of ways to get the sum `x` using the `n` dice. The result can be large, so **return it modulo 10⁹+7**.



## Code(C++)
```cpp
class Solution {
  public:
    int noOfWays(int m, int n, int x) {
        const int mod = 1e9 + 7;
        vector<vector<int>> dp(n + 1, vector<int>(x + 1));
        dp[0][0] = 1;
        for (int i = 1; i <= n; ++i)
            for (int j = 1; j <= x; ++j)
                for (int k = 1; k <= m && k <= j; ++k)
                    dp[i][j] = (dp[i][j] + dp[i - 1][j - k]) % mod;
        return dp[n][x];
    }
};
```

## Code (Java)

```java
class Solution {
    static int noOfWays(int m, int n, int x) {
        int mod = (int)1e9 + 7;
        int[][] dp = new int[n + 1][x + 1];
        dp[0][0] = 1;
        for (int i = 1; i <= n; ++i)
            for (int j = 1; j <= x; ++j)
                for (int k = 1; k <= m && k <= j; ++k)
                    dp[i][j] = (dp[i][j] + dp[i - 1][j - k]) % mod;
        return dp[n][x];
    }
}
```

## Code (Python)

```python
class Solution:
    def noOfWays(self, m, n, x):
        mod = 10**9 + 7
        dp = [[0] * (x + 1) for _ in range(n + 1)]
        dp[0][0] = 1
        for i in range(1, n + 1):
            for j in range(1, x + 1):
                for k in range(1, min(m, j) + 1):
                    dp[i][j] = (dp[i][j] + dp[i - 1][j - k]) % mod
        return dp[n][x]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
