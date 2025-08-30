---
title: "🌟 Celebrity Problem | GFG Solution 🔍"
keywords🏷️: ["🌟 celebrity problem", "🔍 linear search", "📍 two pointers", "📈 matrix traversal", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Celebrity Problem: find the celebrity in a party using optimal linear elimination technique. 🚀"
date: 📅 2025-08-30
---

# *242. The Celebrity Problem*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/the-celebrity-problem/1)

## **🧩 Problem Description**

A celebrity is a person who is known to all but does not know anyone at a party. A party is being organized by some people. A square matrix `mat[][]` of size `n*n` is used to represent people at the party such that if an element of row i and column j is set to 1 it means ith person knows jth person. Your task is to return the **index of the celebrity** in the party, if the celebrity does not exist, return **-1**.

**Note:** Follow 0-based indexing.


## Code(C++)
```cpp
class Solution {
public:
    int celebrity(vector<vector<int>>& m) {
        int n = m.size(), c = 0;
        for (int i = 1; i < n; i++) if (m[c][i]) c = i;
        for (int i = 0; i < n; i++) if (i != c && (m[c][i] || !m[i][c])) return -1;
        return c;
    }
};
```

## Code (Java)

```java
class Solution {
    public int celebrity(int m[][]) {
        int n = m.length, c = 0;
        for (int i = 1; i < n; i++) if (m[c][i] == 1) c = i;
        for (int i = 0; i < n; i++) if (i != c && (m[c][i] == 1 || m[i][c] == 0)) return -1;
        return c;
    }
}
```

## Code (Python3)

```python
class Solution:
    def celebrity(self, m):
        n, c = len(m), 0
        for i in range(1, n):
            if m[c][i]: c = i
        for i in range(n):
            if i != c and (m[c][i] or not m[i][c]): return -1
        return c
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
