---
Difficulty: Hard
Source: 160 Days of Problem Solving
Tags:
  - Graph
---

# 🚀 _Day 107. Minimum Weight Cycle_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/graph-gfg-160/problem/minimum-weight-cycle)


## 💡 **Problem Description:**

Given an **undirected, weighted graph** with **V vertices** numbered from **0 to V-1**, and **E edges**, find the **minimum weight cycle** in the graph.

Each edge is represented by `edges[i] = [u, v, w]` meaning there is an edge between nodes **u and v** with **weight w**.

If **no cycle** exists, return `-1`.

## Code(C++)
```cpp
class Solution {
  public:
    int findMinCycle(int V, vector<vector<int>>& edges) {
        vector<vector<pair<int,int>>> adj(V);
        for (auto& e : edges)
            adj[e[0]].push_back({e[1], e[2]});
        int res = INT_MAX;
        for (int i = 0; i < V; ++i) {
            vector<int> dist(V, 1e9), par(V, -1);
            dist[i] = 0;
            priority_queue<pair<int,int>, vector<pair<int,int>>, greater<pair<int,int>>> pq;
            pq.push({0, i});
            while (!pq.empty()) {
                pair<int,int> top = pq.top(); pq.pop();
                int d = top.first, u = top.second;
                for (int j = 0; j < adj[u].size(); ++j) {
                    int v = adj[u][j].first, w = adj[u][j].second;
                    if (dist[v] > d + w) {
                        dist[v] = d + w;
                        par[v] = u;
                        pq.push({dist[v], v});
                    } else if (par[u] != v && par[v] != u)
                        res = min(res, dist[u] + dist[v] + w);
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
    public int findMinCycle(int V, int[][] E) {
        List<int[]>[] A = new ArrayList[V];
        for (int i = 0; i < V; i++) A[i] = new ArrayList<>();
        for (int[] e : E) A[e[0]].add(new int[]{e[1], e[2]});
        int r = Integer.MAX_VALUE;
        for (int i = 0; i < V; i++) {
            int[] D = new int[V], P = new int[V];
            Arrays.fill(D, (int)1e9);
            Arrays.fill(P, -1);
            D[i] = 0;
            PriorityQueue<int[]> Q = new PriorityQueue<>(Comparator.comparingInt(a -> a[0]));
            Q.add(new int[]{0, i});
            while (!Q.isEmpty()) {
                int[] t = Q.poll(); int d = t[0], u = t[1];
                for (int[] a : A[u]) {
                    int v = a[0], w = a[1];
                    if (D[v] > d + w) {
                        D[v] = d + w; P[v] = u; Q.add(new int[]{D[v], v});
                    } else if (P[u] != v && P[v] != u)
                        r = Math.min(r, D[u] + D[v] + w);
                }
            }
        }
        return r == Integer.MAX_VALUE ? -1 : r;
    }
}
```

## Code (Python)

```python
class Solution:
    def findMinCycle(self, V, edges):
        from heapq import heappush, heappop
        A = [[] for _ in range(V)]
        for u, v, w in edges:
            A[u].append((v, w))
        r = float('inf')
        for i in range(V):
            D = [int(1e9)] * V
            P = [-1] * V
            D[i] = 0
            Q = [(0, i)]
            while Q:
                d, u = heappop(Q)
                for v, w in A[u]:
                    if D[v] > d + w:
                        D[v] = d + w
                        P[v] = u
                        heappush(Q, (D[v], v))
                    elif P[u] != v and P[v] != u:
                        r = min(r, D[u] + D[v] + w)
        return -1 if r == float('inf') else r
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
