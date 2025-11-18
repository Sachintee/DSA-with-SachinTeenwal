---
title: "🛣️ Number of Ways to Arrive at Destination | GFG Solution 🚀"
keywords🏷️: ["🛣️ shortest path", "🔍 Dijkstra", "📍 graph algorithms", "📈 path counting", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to Number of Ways to Arrive at Destination: count all shortest paths from source to destination using Dijkstra's algorithm with path counting. 🚀"
date: 📅 2025-11-18
---

# *322. Number of Ways to Arrive at Destination*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/number-of-ways-to-arrive-at-destination/1)

## **🧩 Problem Description**

You are given an undirected weighted graph with **V vertices** numbered from **0 to V-1** and **E edges**, represented as a 2D array `edges[][]`, where `edges[i] = [ui, vi, timei]` means that there is an undirected edge between nodes `ui` and `vi` that takes `timei` minutes to reach.

Your task is to return **in how many ways** you can travel from node **0** to node **V - 1** in the **shortest amount of time**.


## Code(C++)
```cpp
class Solution {
public:
    int countPaths(int V, vector<vector<int>>& edges) {
        vector<vector<pair<int, int>>> adj(V);
        for (auto& e : edges) {
            adj[e[0]].push_back({e[1], e[2]});
            adj[e[1]].push_back({e[0], e[2]});
        }
        vector<long long> dist(V, LLONG_MAX), ways(V, 0);
        dist[0] = 0;
        ways[0] = 1;
        priority_queue<
            pair<long long, int>,
            vector<pair<long long, int>>,
            greater<>
        > pq;
        pq.push({0, 0});
        const int MOD = 1e9 + 7;
        while (!pq.empty()) {
            auto [d, u] = pq.top();
            pq.pop();
            if (d > dist[u]) continue;
            for (auto [v, w] : adj[u]) {
                if (d + w < dist[v]) {
                    dist[v] = d + w;
                    ways[v] = ways[u];
                    pq.push({dist[v], v});
                }
                else if (d + w == dist[v]) {
                    ways[v] = (ways[v] + ways[u]) % MOD;
                }
            }
        }
        return ways[V - 1];
    }
};
```

## Code (Java)

```java
class Solution {
    public int countPaths(int V, int[][] edges) {
        List<List<int[]>> adj = new ArrayList<>();
        for (int i = 0; i < V; i++) adj.add(new ArrayList<>());
        for (int[] e : edges) {
            adj.get(e[0]).add(new int[]{e[1], e[2]});
            adj.get(e[1]).add(new int[]{e[0], e[2]});
        }
        long[] dist = new long[V], ways = new long[V];
        Arrays.fill(dist, Long.MAX_VALUE);
        dist[0] = 0;
        ways[0] = 1;
        PriorityQueue<long[]> pq =
            new PriorityQueue<>((a, b) -> Long.compare(a[0], b[0]));
        pq.offer(new long[]{0, 0});
        int MOD = 1_000_000_007;
        while (!pq.isEmpty()) {
            long[] top = pq.poll();
            long d = top[0];
            int u = (int) top[1];
            if (d > dist[u]) continue;
            for (int[] nxt : adj.get(u)) {
                int v = nxt[0], w = nxt[1];
                if (d + w < dist[v]) {
                    dist[v] = d + w;
                    ways[v] = ways[u];
                    pq.offer(new long[]{dist[v], v});
                }
                else if (d + w == dist[v]) {
                    ways[v] = (ways[v] + ways[u]) % MOD;
                }
            }
        }
        return (int) ways[V - 1];
    }
}
```

## Code (Python)

```python
from heapq import heappush, heappop
class Solution:
    def countPaths(self, V, edges):
        adj = [[] for _ in range(V)]
        for u, v, w in edges:
            adj[u].append((v, w))
            adj[v].append((u, w))
        dist = [float('inf')] * V
        ways = [0] * V
        dist[0] = 0
        ways[0] = 1
        pq = [(0, 0)]
        MOD = 10**9 + 7
        while pq:
            d, u = heappop(pq)
            if d > dist[u]:
                continue
            for v, w in adj[u]:
                if d + w < dist[v]:
                    dist[v] = d + w
                    ways[v] = ways[u]
                    heappush(pq, (dist[v], v))
                elif d + w == dist[v]:
                    ways[v] = (ways[v] + ways[u]) % MOD
                    
        return ways[V - 1]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
