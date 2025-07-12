---
title: "💰 Gold Mine Problem | GFG Solution 🏆"
keywords🏷️: ["💰 gold mine", "🔍 dynamic programming", "📍 path optimization", "📈 matrix traversal", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Gold Mine Problem: find maximum gold collection path from left to right using dynamic programming optimization. 🚀"
date: 📅 2025-07-12
---

# *193. Gold Mine Problem*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/gold-mine-problem2608/1)

## **🧩 Problem Description**

Given a gold mine called `mat[][]`. Each field in this mine contains a positive integer which is the amount of gold in tons. Initially, the miner can start from any row in the first column. From a given cell, the miner can move:


## Code(C++)
```cpp
class Solution {
public:
    int maxGold(vector<vector<int>>& mat) {
        int n = mat.size(), m = mat[0].size();
        for (int j = m - 2; j >= 0; j--) {
            for (int i = 0; i < n; i++) {
                int mx = 0;
                for (int di = -1; di <= 1; di++) {
                    int ni = i + di;
                    if (ni >= 0 && ni < n) mx = max(mx, mat[ni][j + 1]);
                }
                mat[i][j] += mx;
            }
        }
        int res = 0;
        for (int i = 0; i < n; i++) res = max(res, mat[i][0]);
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public int maxGold(int[][] mat) {
        int n = mat.length, m = mat[0].length;
        for (int j = m - 2; j >= 0; j--) {
            for (int i = 0; i < n; i++) {
                int mx = 0;
                for (int di = -1; di <= 1; di++) {
                    int ni = i + di;
                    if (ni >= 0 && ni < n) mx = Math.max(mx, mat[ni][j + 1]);
                }
                mat[i][j] += mx;
            }
        }
        int res = 0;
        for (int i = 0; i < n; i++) res = Math.max(res, mat[i][0]);
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def maxGold(self, mat):
        n, m = len(mat), len(mat[0])
        for j in range(m - 2, -1, -1):
            for i in range(n):
                mx = 0
                for di in [-1, 0, 1]:
                    ni = i + di
                    if 0 <= ni < n:
                        mx = max(mx, mat[ni][j + 1])
                mat[i][j] += mx
        return max(mat[i][0] for i in range(n))
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
