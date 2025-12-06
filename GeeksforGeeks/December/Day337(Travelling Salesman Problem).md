--- ❤️ ---

# 🚀 _Day 337. Travelling Salesman Problem_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/travelling-salesman-problem2732/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int tsp(vector<vector<int>>& cost) {
        int n = cost.size();
        if (n <= 1) return n ? cost[0][0] : 0;
        int FULL = (1 << n) - 1;
        vector<vector<int>> dp(1 << n, vector<int>(n, INT_MAX));
        dp[1][0] = 0;
        for (int mask = 1; mask <= FULL; mask++) {
            for (int i = 0; i < n; i++) {
                if (!(mask & (1 << i)) || dp[mask][i] == INT_MAX) continue;
                for (int j = 0; j < n; j++) {
                    if (mask & (1 << j)) continue;
                    int nxt = mask | (1 << j);
                    dp[nxt][j] = min(dp[nxt][j], dp[mask][i] + cost[i][j]);
                }
            }
        }
        int ans = INT_MAX;
        for (int i = 0; i < n; i++)
            if (dp[FULL][i] != INT_MAX)
                ans = min(ans, dp[FULL][i] + cost[i][0]);
        return ans;
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
