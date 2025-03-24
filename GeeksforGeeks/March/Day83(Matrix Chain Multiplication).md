---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Dynamic Programming
  - Matrix
---

# 🚀 _Day 83. Matrix Chain Multiplication_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/matrix-chain-multiplication0303/1)

## 💡 **Problem Description:** 

Given an array `arr[]` where the `i`th matrix has the dimensions **(arr[i-1] × arr[i])** for `i ≥ 1`, find the most efficient way to multiply these matrices together. The efficient way is the one that involves the least number of scalar multiplications.

You need to find the **minimum number of multiplications** required to multiply the matrices.


## Code(C++)
```cpp
class Solution {
public:
    int matrixMultiplication(vector<int> &arr) {
        int n = arr.size();
        vector<vector<int>> dp(n, vector<int>(n, 0));

        for (int len = 2; len < n; len++) {
            for (int i = 1, j = len; j < n; i++, j++) {
                dp[i][j] = INT_MAX;
                for (int k = i; k < j; k++)
                    dp[i][j] = min(dp[i][j], arr[i - 1] * arr[k] * arr[j] + dp[i][k] + dp[k + 1][j]);
            }
        }
        return dp[1][n - 1];
    }
};
```

## Code (Java)

```java
class Solution {
    static int matrixMultiplication(int[] arr) {
        int n = arr.length;
        int[][] dp = new int[n][n];

        for (int len = 2; len < n; len++)
            for (int i = 1, j = len; j < n; i++, j++) {
                dp[i][j] = Integer.MAX_VALUE;
                for (int k = i; k < j; k++)
                    dp[i][j] = Math.min(dp[i][j], arr[i - 1] * arr[k] * arr[j] + dp[i][k] + dp[k + 1][j]);
            }
        return dp[1][n - 1];
    }
}
```

## Code (Python)

```python
class Solution:
    def matrixMultiplication(self, arr):
        n, dp = len(arr), [[0] * len(arr) for _ in range(len(arr))]

        for l in range(2, n):
            for i in range(1, n - l + 1):
                j, dp[i][i + l - 1] = i + l - 1, float('inf')
                for k in range(i, j):
                    dp[i][j] = min(dp[i][j], arr[i - 1] * arr[k] * arr[j] + dp[i][k] + dp[k + 1][j])
        
        return dp[1][n - 1]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
