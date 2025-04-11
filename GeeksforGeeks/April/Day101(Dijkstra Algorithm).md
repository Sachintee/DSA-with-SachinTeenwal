---
Difficulty: Medium
Source: 160 Days of Problem Solving
Tags:
  - Graph
---

# 🚀 _Day 101. Dijkstra’s Algorithm_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/graph-gfg-160/problem/implementing-dijkstra-set-1-adjacency-matrix)

## 💡 **Problem Description:**

Given an **undirected, weighted graph** with **V** vertices numbered from **0** to **V-1** and **E** edges, represented by a 2D array `edges[][]` (where each `edges[i] = [u, v, w]` represents an edge between nodes **u** and **v** with weight **w**), find the shortest distance from a given source vertex **src** to all other vertices.  
Return an array of integers where the *ith* element denotes the shortest distance from the source vertex **src** to vertex **i**.

## Code(C++)
```cpp
class Solution {
  public:
    vector<int> dijkstra(int V, vector<vector<int>> &edges, int src) {
        vector<vector<pair<int, int>>> g(V);
        for (auto &e : edges) g[e[0]].emplace_back(e[1], e[2]);
        vector<int> d(V, 1e9); d[src] = 0;
        priority_queue<pair<int, int>, vector<pair<int, int>>, greater<>> q;
        q.emplace(0, src);
        while (!q.empty()) {
            auto p = q.top(); q.pop();
            if (p.first > d[p.second]) continue;
            for (auto &x : g[p.second])
                if (p.first + x.second < d[x.first])
                    q.emplace(d[x.first] = p.first + x.second, x.first);
        }
        return d;
    }
};
```

## Code (Java)

```java
class Solution {
    public int[] dijkstra(int V, int[][] edges, int src) {
        List<int[]>[] g = new List[V];
        for (int i = 0; i < V; i++) g[i] = new ArrayList<>();
        for (int[] e : edges) g[e[0]].add(new int[]{e[1], e[2]});
        int[] d = new int[V];
        Arrays.fill(d, Integer.MAX_VALUE);
        d[src] = 0;
        PriorityQueue<int[]> q = new PriorityQueue<>(Comparator.comparingInt(a -> a[0]));
        q.offer(new int[]{0, src});
        while (!q.isEmpty()) {
            int[] p = q.poll();
            if (p[0] > d[p[1]]) continue;
            for (int[] x : g[p[1]])
                if (p[0] + x[1] < d[x[0]])
                    q.offer(new int[]{d[x[0]] = p[0] + x[1], x[0]});
        }
        return d;
    }
}
```

## Code (Python)

```python
class Solution:
    def dijkstra(self, V, edges, src):
        from heapq import heappush, heappop
        g = [[] for _ in range(V)]
        for u, v, w in edges:
            g[u].append((v, w))
        d = [float('inf')] * V
        d[src] = 0
        q = [(0, src)]
        while q:
            du, u = heappop(q)
            if du > d[u]: continue
            for v, w in g[u]:
                if du + w < d[v]:
                    d[v] = du + w
                    heappush(q, (d[v], v))
        return d
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
