---
Difficulty: Medium
Source: 160 Days of Problem Solving
Tags:
  - Graph
---

# 🚀 _Day 97. Directed Graph Cycle_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/graph-gfg-160/problem/detect-cycle-in-a-directed-graph)

> Note: Sorry for uploading late, my Final Sem exam is going on.

## 💡 **Problem Description:**

Given a **Directed Graph** with **V** vertices (numbered from 0 to V-1) and **E** edges, determine whether the graph contains any cycle.  
The graph is represented as a 2D vector `edges[][]`, where each entry `edges[i] = [u, v]` denotes an edge from vertex **u** to **v**.


## Code(C++)
```cpp
class Solution {
public:
    bool isCyclic(int V, vector<vector<int>>& edges) {
        vector<vector<int>> g(V);
        vector<int> in(V);
        for (auto& e : edges) g[e[0]].push_back(e[1]), in[e[1]]++;
        queue<int> q;
        for (int i = 0; i < V; i++) if (!in[i]) q.push(i);
        int c = 0;
        while (!q.empty()) {
            int u = q.front(); q.pop(); c++;
            for (int v : g[u]) if (--in[v] == 0) q.push(v);
        }
        return c != V;
    }
};
```

## Code (Java)

```java
class Solution {
    public boolean isCyclic(int V, int[][] edges) {
        List<Integer>[] g = new ArrayList[V];
        int[] in = new int[V];
        for (int i = 0; i < V; i++) g[i] = new ArrayList<>();
        for (int[] e : edges) { g[e[0]].add(e[1]); in[e[1]]++; }
        Queue<Integer> q = new ArrayDeque<>();
        for (int i = 0; i < V; i++) if (in[i] == 0) q.add(i);
        int c = 0;
        while (!q.isEmpty()) {
            int u = q.poll(); c++;
            for (int v : g[u]) if (--in[v] == 0) q.add(v);
        }
        return c != V;
    }
}
```

## Code (Python)

```python
class Solution:
    def isCycle(self, V, edges):
        g = [[] for _ in range(V)]
        in_d = [0]*V
        for u, v in edges: g[u].append(v); in_d[v] += 1
        q = [i for i in range(V) if in_d[i] == 0]
        c = 0
        while q:
            u = q.pop(0); c += 1
            for v in g[u]:
                in_d[v] -= 1
                if in_d[v] == 0: q.append(v)
        return c != V
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
