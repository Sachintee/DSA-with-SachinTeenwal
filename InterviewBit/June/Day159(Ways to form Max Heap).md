--- ❤️ ---

# 🚀 _Day 159. Ways to form Max Heap_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/ways-to-form-max-heap/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <bits/stdc++.h>
using namespace std;

const int MOD = 1e9 + 7;
int nck[105][105];
int log2val[105];
int dp[105];

void precompute() {
    // Precompute nCk
    for (int n = 0; n <= 100; n++) {
        for (int k = 0; k <= n; k++) {
            if (k == 0 || k == n)
                nck[n][k] = 1;
            else
                nck[n][k] = (nck[n - 1][k - 1] + nck[n - 1][k]) % MOD;
        }
    }

    // Precompute log2
    log2val[0] = -1;
    for (int i = 1; i <= 100; i++)
        log2val[i] = log2val[i / 2] + 1;
}

int getLeft(int n) {
    if (n == 1) return 0;

    int h = log2val[n];
    int maxNodesAtH = 1 << h;
    int nodesLast = n - ((1 << h) - 1);

    if (nodesLast >= maxNodesAtH / 2)
        return (1 << h) - 1;
    else
        return (1 << h) - 1 - ((maxNodesAtH / 2) - nodesLast);
}

int numberOfHeaps(int n) {
    if (n <= 1) return 1;
    if (dp[n] != -1) return dp[n];

    int L = getLeft(n);
    long long ans = nck[n - 1][L];
    ans = (ans * numberOfHeaps(L)) % MOD;
    ans = (ans * numberOfHeaps(n - 1 - L)) % MOD;

    return dp[n] = ans;
}

int solve(int A) {
    memset(dp, -1, sizeof(dp));
    precompute();
    return numberOfHeaps(A);
}

// Example usage:
// int main() {
//     int A = 10;
//     cout << solve(A) << endl; // Output: 3360
//     return 0;
// }

```

## Code (Java)

```java
import java.util.*;

public class Solution {
    static final int MOD = 1000000007;
    static int[][] nck = new int[105][105];
    static int[] log2 = new int[105];
    static int[] dp = new int[105];

    public Solution() {
        Arrays.fill(dp, -1);
        precompute();
    }

    void precompute() {
        // nCk precomputation
        for (int n = 0; n <= 100; n++) {
            for (int k = 0; k <= n; k++) {
                if (k == 0 || k == n) {
                    nck[n][k] = 1;
                } else {
                    nck[n][k] = (nck[n - 1][k - 1] + nck[n - 1][k]) % MOD;
                }
            }
        }

        // log2 precomputation
        log2[0] = -1;
        for (int i = 1; i <= 100; i++) {
            log2[i] = log2[i / 2] + 1;
        }
    }

    int getLeft(int n) {
        if (n == 1) return 0;

        int h = log2[n];
        int maxNodesAtH = 1 << h;
        int nodesLast = n - ((1 << h) - 1);

        if (nodesLast >= maxNodesAtH / 2)
            return (1 << h) - 1;
        else
            return (1 << h) - 1 - ((maxNodesAtH / 2) - nodesLast);
    }

    int numberOfHeaps(int n) {
        if (n <= 1) return 1;
        if (dp[n] != -1) return dp[n];

        int L = getLeft(n);
        long ans = nck[n - 1][L];
        ans = (ans * numberOfHeaps(L)) % MOD;
        ans = (ans * numberOfHeaps(n - 1 - L)) % MOD;

        return dp[n] = (int) ans;
    }

    public int solve(int A) {
        return numberOfHeaps(A);
    }

    // Example usage:
    // public static void main(String[] args) {
    //     Solution s = new Solution();
    //     System.out.println(s.solve(10)); // Output: 3360
    // }
}

```

## Code (Python)

```python
import math
import sys
sys.setrecursionlimit(10000)

class Solution:
    MOD = 10**9 + 7

    def __init__(self):
        self.dp = {}
        self.nck = {}
        self.log2 = [0] * 101
        self.precompute()

    def precompute(self):
        # Precompute log2
        for i in range(2, 101):
            self.log2[i] = self.log2[i // 2] + 1

        # Precompute nCk
        for n in range(0, 101):
            self.nck[n] = {}
            for k in range(0, n + 1):
                if k == 0 or k == n:
                    self.nck[n][k] = 1
                else:
                    self.nck[n][k] = (self.nck[n - 1][k - 1] + self.nck[n - 1][k]) % self.MOD

    def getLeftCount(self, n):
        if n == 1:
            return 0

        h = self.log2[n]
        maxNodesAtH = 1 << h  # 2^h
        actualNodesLast = n - ((1 << h) - 1)

        if actualNodesLast >= maxNodesAtH // 2:
            return (1 << h) - 1
        else:
            return (1 << h) - 1 - ((maxNodesAtH // 2) - actualNodesLast)

    def numberOfHeaps(self, n):
        if n <= 1:
            return 1
        if n in self.dp:
            return self.dp[n]

        L = self.getLeftCount(n)
        result = (self.nck[n - 1][L] * self.numberOfHeaps(L)) % self.MOD
        result = (result * self.numberOfHeaps(n - 1 - L)) % self.MOD

        self.dp[n] = result
        return result

    def solve(self, A):
        return self.numberOfHeaps(A)

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
