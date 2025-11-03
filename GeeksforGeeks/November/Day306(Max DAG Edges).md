---
title: "🧮 Max DAG Edges | GFG Solution 🔍"
keywords🏷️: ["🧮 Max DAG Edges", "🔍 DAG", "📈 Topological Order", "📘 GFG", "🏁 competitive programming", "📚 DSA", "🚀 Graph Theory"]
description: "✅ GFG solution to the Max DAG Edges problem: find maximum number of edges that can be added to a Directed Acyclic Graph (DAG) without forming cycles. 🚀"
date: 📅 2025-11-02
---

# *306. Max DAG Edges*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/max-dag-edges/1)

## **🧩 Problem Description**

Given a directed acyclic graph (DAG) with `V` vertices numbered from 0 to V-1 and `E` edges, represented as a 2D array `edges[][]`, where each entry `edges[i] = [u, v]` denotes a directed edge from vertex `u` to vertex `v`, find the **maximum number of additional edges** that can be added to the graph without forming any cycles.

**Note:** The resulting graph must remain a DAG, meaning that adding any further edge would not create a cycle.


## Code(C++)
```cpp
class Solution {
public:
    int maxEdgesToAdd(int V, vector<vector<int>>& edges) {
        return V * (V - 1) / 2 - edges.size();
    }
};
```

## Code (Java)

```java
class Solution {
    public int maxEdgesToAdd(int V, int[][] edges) {
        return V * (V - 1) / 2 - edges.length;
    }
}
```

## Code (Python)

```python
class Solution:
    def maxEdgesToAdd(self, V, edges):
        return V * (V - 1) // 2 - len(edges)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
