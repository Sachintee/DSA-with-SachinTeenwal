---
title: "🌳 Graph Diameter | GFG Solution 🔍"
keywords🏷️: ["🌳 graph diameter", "🔍 BFS", "📍 tree diameter", "📈 two BFS", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Graph Diameter problem: find the longest path in an undirected tree using two BFS traversals. 🚀"
date: 📅 2025-10-29
---

# *302. Graph Diameter*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/diameter-of-a-graph/1)

## **🧩 Problem Description**

You are given an undirected connected graph with `V` vertices numbered from `0` to `V-1` and `E` edges, represented as a 2D array `edges[][]`, where each element `edges[i] = [u, v]` represents an undirected edge between vertex `u` and vertex `v`.

Find the **diameter** of the graph. The diameter of a graph (sometimes called the width) is the **number of edges** on the longest path between two vertices in the graph.

**Note:** Graph does not contain any cycle (it's a tree).


## Code(C++)
```cpp
class Solution {
public:
    int diameter(int V, vector<vector<int>>& edges) {
        vector<vector<int>> adj(V);
        for (auto& e : edges) {
            adj[e[0]].push_back(e[1]);
            adj[e[1]].push_back(e[0]);
        }
        auto bfs = [&](int src) {
            vector<int> d(V, -1);
            queue<int> q;
            q.push(src);
            d[src] = 0;
            int far = src, maxD = 0;
            while (!q.empty()) {
                int u = q.front();
                q.pop();
                for (int v : adj[u]) {
                    if (d[v] == -1) {
                        d[v] = d[u] + 1;
                        q.push(v);
                        if (d[v] > maxD) {
                            maxD = d[v];
                            far = v;
                        }
                    }
                }
            }
            return make_pair(far, maxD);
        };
        auto [end1, _] = bfs(0);
        auto [end2, diam] = bfs(end1);
        return diam;
    }
};
```

## Code (Java)

```java
class Solution {
    public int diameter(int V, int[][] edges) {
        List<List<Integer>> adj = new ArrayList<>();
        for (int i = 0; i < V; i++) adj.add(new ArrayList<>());
        for (int[] e : edges) {
            adj.get(e[0]).add(e[1]);
            adj.get(e[1]).add(e[0]);
        }
        int[] first = bfs(0, adj);
        int[] second = bfs(first[0], adj);
        return second[1];
    }
    private int[] bfs(int src, List<List<Integer>> adj) {
        int n = adj.size();
        int[] dist = new int[n];
        Arrays.fill(dist, -1);
        Queue<Integer> q = new LinkedList<>();
        q.add(src);
        dist[src] = 0;
        int far = src, maxD = 0;
        while (!q.isEmpty()) {
            int u = q.poll();
            for (int v : adj.get(u)) {
                if (dist[v] == -1) {
                    dist[v] = dist[u] + 1;
                    q.add(v);
                    if (dist[v] > maxD) {
                        maxD = dist[v];
                        far = v;
                    }
                }
            }
        }
        return new int[]{far, maxD};
    }
}
```

## Code (Python)

```python
class Solution:
    def diameter(self, V, edges):
        adj = [[] for _ in range(V)]
        for u, v in edges:
            adj[u].append(v)
            adj[v].append(u)
        def bfs(src):
            dist = [-1] * V
            q = deque([src])
            dist[src] = 0
            far, maxD = src, 0
            while q:
                u = q.popleft()
                for v in adj[u]:
                    if dist[v] == -1:
                        dist[v] = dist[u] + 1
                        q.append(v)
                        if dist[v] > maxD:
                            maxD = dist[v]
                            far = v
            return far, maxD
        end1, _ = bfs(0)
        _, diam = bfs(end1)
        return diam
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
