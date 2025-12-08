--- ❤️ ---

# 🚀 _Day 342. Brackets in Matrix Chain Multiplication_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/brackets-in-matrix-chain-multiplication1024/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    string build(int i, int j, vector<vector<int>> &bracket) {
        if (i == j)
            return string(1, 'A' + i - 1);

        return "(" + build(i, bracket[i][j], bracket) 
                   + build(bracket[i][j] + 1, j, bracket)
                   + ")";
    }

    string matrixChainOrder(vector<int> &arr) {
        int n = arr.size();
        vector<vector<long long>> dp(n, vector<long long>(n, 0));
        vector<vector<int>> bracket(n, vector<int>(n, 0));

        // L = chain length
        for (int L = 2; L < n; L++) {
            for (int i = 1; i < n - L + 1; i++) {
                int j = i + L - 1;
                dp[i][j] = LLONG_MAX;

                for (int k = i; k < j; k++) {
                    long long cost = dp[i][k] + dp[k+1][j] + 1LL * arr[i-1] * arr[k] * arr[j];

                    if (cost < dp[i][j]) {
                        dp[i][j] = cost;
                        bracket[i][j] = k;
                    }
                }
            }
        }

        return build(1, n-1, bracket);
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
