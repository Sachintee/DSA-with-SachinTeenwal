---
title: "🔄 Shortest Cycle | GFG Solution 🔍"
keywords🏷️: ["🔄 shortest cycle", "🔍 BFS", "📍 graph traversal", "📈 cycle detection", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Shortest Cycle in Undirected Graph problem: find minimum length cycle in an undirected graph using multi-source BFS technique. 🚀"
date: 📅 2025-10-31
---

# *304. Shortest Cycle*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/shortest-cycle/1)

## **🧩 Problem Description**

You are given an undirected graph with `V` vertices numbered from 0 to V-1 and `E` edges, represented as a 2D array `edges[][]`, where each element `edges[i] = [u, v]` represents an undirected edge between vertex `u` and `v`.

Find the length of the **shortest cycle** in the graph. If the graph does not contain any cycle, return `-1`.

A cycle is a path that starts and ends at the same vertex without repeating any edge or vertex (except the start/end vertex). The shortest cycle is the one with the minimum number of edges.


## Code(C++)
```cpp
class Solution {
public:
    int shortCycle(int V, vector<vector<int>> &edges) {
        vector<vector<int>> adj(V);
        for (auto &e : edges) {
            adj[e[0]].push_back(e[1]);
            adj[e[1]].push_back(e[0]);
        }
        int res = INT_MAX;
        for (int i = 0; i < V; i++) {
            vector<int> d(V, -1), p(V, -1);
            queue<int> q;
            d[i] = 0;
            q.push(i);
            while (!q.empty()) {
                int u = q.front();
                q.pop();
                for (int v : adj[u]) {
                    if (d[v] == -1) {
                        d[v] = d[u] + 1;
                        p[v] = u;
                        q.push(v);
                    } else if (p[u] != v) res = min(res, d[u] + d[v] + 1);
                }
            }
        }
        return res == INT_MAX ? -1 : res;
    }
};
```

## Code (Java)

```java
class Solution {
    public int shortCycle(int V, int[][] edges) {
        List<List<Integer>> adj = new ArrayList<>();
        for (int i = 0; i < V; i++) adj.add(new ArrayList<>());
        for (int[] e : edges) {
            adj.get(e[0]).add(e[1]);
            adj.get(e[1]).add(e[0]);
        }
        int res = Integer.MAX_VALUE;
        for (int i = 0; i < V; i++) {
            int[] d = new int[V];
            int[] p = new int[V];
            Arrays.fill(d, -1);
            Arrays.fill(p, -1);
            Queue<Integer> q = new LinkedList<>();
            d[i] = 0;
            q.offer(i);
            while (!q.isEmpty()) {
                int u = q.poll();
                for (int v : adj.get(u)) {
                    if (d[v] == -1) {
                        d[v] = d[u] + 1;
                        p[v] = u;
                        q.offer(v);
                    } else if (p[u] != v) res = Math.min(res, d[u] + d[v] + 1);
                }
            }
        }
        return res == Integer.MAX_VALUE ? -1 : res;
    }
}
```

## Code (Python)

```python
class Solution:
    def shortCycle(self, V, edges):
        from collections import deque
        adj = [[] for _ in range(V)]
        for u, v in edges:
            adj[u].append(v)
            adj[v].append(u)
        res = float('inf')
        for i in range(V):
            d = [-1] * V
            p = [-1] * V
            q = deque([i])
            d[i] = 0
            while q:
                u = q.popleft()
                for v in adj[u]:
                    if d[v] == -1:
                        d[v] = d[u] + 1
                        p[v] = u
                        q.append(v)
                    elif p[u] != v:
                        res = min(res, d[u] + d[v] + 1)
        return -1 if res == float('inf') else res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
