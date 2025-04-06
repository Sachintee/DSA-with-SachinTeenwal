---
Difficulty: Medium
Source: 160 Days of Problem Solving
Tags:
  - Graph
---

# 🚀 _Day 96. Topological sort_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/graph-gfg-160/problem/topological-sort)  

## 💡 **Problem Description:**

Given a **Directed Acyclic Graph (DAG)** with V vertices (numbered from 0 to V-1) and E directed edges (represented as a 2D list where each edge is given as `[u, v]` indicating an edge from u to v), return a topological ordering of the vertices.  

A **topological sort** of a DAG is a linear ordering of vertices such that for every directed edge u -> v, vertex u appears before vertex v in the ordering.  
Note: Since there can be multiple valid topological orders, you may return any one of them. The returned ordering is considered correct if for every directed edge u -> v, u comes before v.


## Code(C++)
```cpp
class Solution {
public:
    vector<int> topoSort(int V, vector<vector<int>>& edges) {
        vector<vector<int>> adj(V);
        vector<int> in(V, 0), res;
        for (auto &e : edges) {
            adj[e[0]].push_back(e[1]);
            in[e[1]]++;
        }
        queue<int> q;
        for (int i = 0; i < V; i++)
            if (!in[i])
                q.push(i);
        while (!q.empty()) {
            int u = q.front();
            q.pop();
            res.push_back(u);
            for (int v : adj[u])
                if (--in[v] == 0)
                    q.push(v);
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public static ArrayList<Integer> topoSort(int V, int[][] edges) {
        ArrayList<ArrayList<Integer>> g = new ArrayList<>();
        int[] in = new int[V];
        ArrayList<Integer> res = new ArrayList<>();
        for (int i = 0; i < V; i++) g.add(new ArrayList<>());
        for (int[] e : edges) {
            g.get(e[0]).add(e[1]);
            in[e[1]]++;
        }
        Queue<Integer> q = new LinkedList<>();
        for (int i = 0; i < V; i++) if (in[i] == 0) q.add(i);
        while (!q.isEmpty()) {
            int u = q.poll();
            res.add(u);
            for (int v : g.get(u)) if (--in[v] == 0) q.add(v);
        }
        return res;
    }
}
```

## Code (Python)

```python
from collections import deque

class Solution:
    def topoSort(self, V, edges):
        g = [[] for _ in range(V)]
        in_deg = [0] * V
        res = []
        for u, v in edges:
            g[u].append(v)
            in_deg[v] += 1
        q = deque(i for i in range(V) if in_deg[i] == 0)
        while q:
            u = q.popleft()
            res.append(u)
            for v in g[u]:
                in_deg[v] -= 1
                if in_deg[v] == 0:
                    q.append(v)
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
