---
title: "🔲 Max Rectangle | GFG Solution 🔍"
keywords🏷️: ["🔲 max rectangle", "📊 histogram", "📍 stack", "🔄 dynamic programming", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Max Rectangle problem: find maximum area rectangle in binary matrix using largest rectangle in histogram approach with stack optimization. 🚀"
date: 📅 2025-09-21
---

# *264. Max Rectangle*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/max-rectangle/1)

## **🧩 Problem Description**

You are given a 2D binary matrix `mat[][]`, where each cell contains either 0 or 1. Your task is to find the **maximum area of a rectangle** that can be formed using only 1's within the matrix.

A rectangle is formed by selecting a submatrix where all elements are 1. The goal is to find the rectangle with the maximum possible area.


## Code(C++)
```cpp
class Solution {
public:
    int maxArea(vector<vector<int>>& mat) {
        int n = mat.size(), m = mat[0].size(), res = 0;
        vector<int> h(m, 0);
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < m; j++) 
                h[j] = mat[i][j] ? h[j] + 1 : 0;
            stack<int> st;
            for (int j = 0; j <= m; j++) {
                int cur = j == m ? 0 : h[j];
                while (!st.empty() && h[st.top()] > cur) {
                    int tp = st.top(); st.pop();
                    int w = st.empty() ? j : j - st.top() - 1;
                    res = max(res, h[tp] * w);
                }
                st.push(j);
            }
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    static int maxArea(int mat[][]) {
        int n = mat.length, m = mat[0].length, res = 0;
        int[] h = new int[m];
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < m; j++)
                h[j] = mat[i][j] == 1 ? h[j] + 1 : 0;
            Stack<Integer> st = new Stack<>();
            for (int j = 0; j <= m; j++) {
                int cur = j == m ? 0 : h[j];
                while (!st.isEmpty() && h[st.peek()] > cur) {
                    int tp = st.pop();
                    int w = st.isEmpty() ? j : j - st.peek() - 1;
                    res = Math.max(res, h[tp] * w);
                }
                st.push(j);
            }
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def maxArea(self, mat):
        n, m, res = len(mat), len(mat[0]), 0
        h = [0] * m
        for i in range(n):
            for j in range(m):
                h[j] = h[j] + 1 if mat[i][j] else 0
            st = []
            for j in range(m + 1):
                cur = 0 if j == m else h[j]
                while st and h[st[-1]] > cur:
                    tp = st.pop()
                    w = j if not st else j - st[-1] - 1
                    res = max(res, h[tp] * w)
                st.append(j)
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
