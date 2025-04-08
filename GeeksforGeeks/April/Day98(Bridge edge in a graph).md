---
Difficulty: Medium
Source: 160 Days of Problem Solving
Tags:
  - Graph
---

# 🚀 _Day 98. Bridge edge in a graph_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/graph-gfg-160/problem/bridge-edge-in-graph)

## 💡 **Problem Description:**

Given an **undirected graph** with **V** vertices and **E** edges, along with a specific edge connecting vertices **c** and **d**, the task is to determine whether this edge is a **bridge**. An edge (c–d) is considered a bridge if removing it increases the number of connected components in the graph, meaning that vertices c and d were part of the same connected component before, but become disconnected after its removal.


## Code(C++)
```cpp
class Solution {
  public:
    void dfs(vector<vector<int>> &adj, int u, vector<bool> &vis) {
        vis[u] = true;
        for (int v : adj[u])
            if (!vis[v]) dfs(adj, v, vis);
    }

    bool isBridge(int V, vector<vector<int>> &edges, int c, int d) {
        vector<vector<int>> adj(V);
        for (auto &e : edges)
            if (!(e[0] == c && e[1] == d || e[0] == d && e[1] == c))
                adj[e[0]].push_back(e[1]), adj[e[1]].push_back(e[0]);
        vector<bool> vis(V);
        dfs(adj, c, vis);
        return !vis[d];
    }
};
```

## Code (Java)

```java
class Solution {
    void dfs(List<List<Integer>> g, boolean[] vis, int u) {
        vis[u] = true;
        for (int v : g.get(u)) if (!vis[v]) dfs(g, vis, v);
    }

    public boolean isBridge(int V, int[][] edges, int c, int d) {
        List<List<Integer>> g = new ArrayList<>();
        for (int i = 0; i < V; i++) g.add(new ArrayList<>());
        for (int[] e : edges)
            if (!(e[0] == c && e[1] == d || e[0] == d && e[1] == c)) {
                g.get(e[0]).add(e[1]);
                g.get(e[1]).add(e[0]);
            }
        boolean[] vis = new boolean[V];
        dfs(g, vis, c);
        return !vis[d];
    }
}
```

## Code (Python)

```python
class Solution:
    def dfs(self, g, vis, u):
        vis[u] = 1
        for v in g[u]:
            if not vis[v]: self.dfs(g, vis, v)

    def isBridge(self, V, edges, c, d):
        g = [[] for _ in range(V)]
        for u, v in edges:
            if (u, v) != (c, d) and (v, u) != (c, d):
                g[u].append(v)
                g[v].append(u)
        vis = [0] * V
        self.dfs(g, vis, c)
        return not vis[d]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
