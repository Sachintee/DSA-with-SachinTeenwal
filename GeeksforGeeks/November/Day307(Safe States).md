---
title: "🔒 Safe States | GFG Solution 🔍"
keywords🏷️: ["🔒 safe states", "🔍 graph algorithms", "📍 topological sort", "📈 BFS", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Safe States problem: find all safe nodes in a directed graph where every path leads to a terminal node using reverse topological sort technique. 🚀"
date: 📅 2025-11-03
---

# *307. Safe States*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/eventual-safe-states/1)

## **🧩 Problem Description**

You are given a directed graph with `V` vertices numbered from `0` to `V-1` and `E` directed edges, represented as a 2D array `edges[][]`, where each element `edges[i] = [u, v]` represents a directed edge from vertex `u` to vertex `v`. Your task is to return all **Safe Nodes** of the graph.

A vertex with no outgoing edges is called a **terminal node**. A vertex is considered **safe** if every path starting from it eventually reaches a terminal node (i.e., it doesn't lead to a cycle or get stuck in an infinite loop).


## Code(C++)
```cpp
class Solution {
public:
    vector<int> safeNodes(int V, vector<vector<int>>& edges) {
        vector<int> out(V), safe(V);
        vector<vector<int>> g(V);
        for (auto& e : edges) out[e[0]]++, g[e[1]].push_back(e[0]);
        queue<int> q;
        for (int i = 0; i < V; i++) if (!out[i]) q.push(i), safe[i] = 1;
        while (!q.empty()) {
            int u = q.front(); q.pop();
            for (int v : g[u]) if (!safe[v] && --out[v] == 0) q.push(v), safe[v] = 1;
        }
        vector<int> res;
        for (int i = 0; i < V; i++) if (safe[i]) res.push_back(i);
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<Integer> safeNodes(int V, int[][] edges) {
        int[] out = new int[V];
        List<List<Integer>> g = new ArrayList<>();
        for (int i = 0; i < V; i++) g.add(new ArrayList<>());
        for (int[] e : edges) { out[e[0]]++; g.get(e[1]).add(e[0]); }
        Queue<Integer> q = new LinkedList<>();
        boolean[] safe = new boolean[V];
        for (int i = 0; i < V; i++) if (out[i] == 0) { q.add(i); safe[i] = true; }
        while (!q.isEmpty()) {
            int u = q.poll();
            for (int v : g.get(u)) if (!safe[v] && --out[v] == 0) { q.add(v); safe[v] = true; }
        }
        ArrayList<Integer> res = new ArrayList<>();
        for (int i = 0; i < V; i++) if (safe[i]) res.add(i);
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def safeNodes(self, V, edges):
        out, g = [0] * V, [[] for _ in range(V)]
        for u, v in edges: out[u] += 1; g[v].append(u)
        q, safe = [], [0] * V
        for i in range(V):
            if not out[i]: q.append(i); safe[i] = 1
        for u in q:
            for v in g[u]:
                if not safe[v]:
                    out[v] -= 1
                    if not out[v]: q.append(v); safe[v] = 1
        return [i for i in range(V) if safe[i]]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
