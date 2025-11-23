---
title: "🪨 Maximum Stone Removal | GFG Solution 🔍"
keywords🏷️: ["🪨 stone removal", "🔗 union find", "🌳 graph connectivity", "📊 DSU", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Maximum Stone Removal problem: find maximum number of removable stones sharing rows or columns using Union-Find and graph connectivity techniques. 🚀"
date: 📅 2025-11-23
---

# *327. Maximum Stone Removal*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/maximum-stone-removal-1662179442/1)

## **🧩 Problem Description**

You are given a 2D array `stones[][]` of non-negative integers where `stones[i] = [xi, yi]` represents the location of the ith stone on a 2D plane. Your task is to return the **maximum possible number of stones** that you can remove.

A stone can be removed if it shares either the **same row** or the **same column** as another stone that has not been removed. The goal is to maximize the number of stones removed while following this constraint.

**Note:** Each coordinate point may have at most one stone.


## Code(C++)
```cpp
class Solution {
    int find(int x, vector<int>& p) {
        return p[x] < 0 ? x : p[x] = find(p[x], p);
    }
    void unite(int x, int y, vector<int>& p) {
        x = find(x, p); y = find(y, p);
        if (x != y) p[x] = y;
    }
public:
    int maxRemove(vector<vector<int>>& stones) {
        int n = stones.size();
        vector<int> p(20002, -1);
        for (auto& s : stones) unite(s[0], s[1] + 10001, p);
        unordered_set<int> roots;
        for (auto& s : stones) roots.insert(find(s[0], p));
        return n - roots.size();
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
