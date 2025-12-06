--- ❤️ ---

# 🚀 _Day 338. Optimal Binary Search Tree_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/optimal-binary-search-tree2214/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int minCost(vector<int> &keys, vector<int> &freq) {
        int n = keys.size();
        vector<vector<int>> dp(n, vector<int>(n, 0));
        vector<int> ps(n + 1, 0);
        for (int i = 0; i < n; i++) ps[i + 1] = ps[i] + freq[i];
        for (int i = 0; i < n; i++) dp[i][i] = freq[i];
        for (int l = 2; l <= n; l++) {
            for (int i = 0; i <= n - l; i++) {
                int j = i + l - 1;
                dp[i][j] = INT_MAX;
                int fsum = ps[j + 1] - ps[i];
                for (int r = i; r <= j; r++) {
                    int c = (r > i ? dp[i][r - 1] : 0) + (r < j ? dp[r + 1][j] : 0) + fsum;
                    dp[i][j] = min(dp[i][j], c);
                }
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
