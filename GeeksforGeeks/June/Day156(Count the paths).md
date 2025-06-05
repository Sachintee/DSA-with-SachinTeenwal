---
title: "🛤️ Count the paths | GFG Solution 🚦"
keywords🏷️: ["🛤️ count paths", "🌳 DAG", "🔢 topological sort", "🧮 dynamic programming", "📈 graph traversal", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to Count Paths in DAG problem: count total distinct paths from source to destination in a directed acyclic graph using topological sorting and DP. 🚀"
date: 📅 2025-06-05
---

# *156. Count the paths*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/count-the-paths4332/1)

## **🧩 Problem Description**

Given a Directed Acyclic Graph (DAG) with `V` nodes labeled from `0` to `V-1`, and a list of directed edges `edges[i] = [u, v]` representing a directed edge from node `u` to node `v`, find the total number of distinct paths from a given source node `S` to a destination node `D`.


## Code(C++)
```cpp
class Solution {
  public:
    int countPaths(vector<vector<int>>& E, int V, int S, int D) {
        vector<vector<int>> G(V); vector<int> I(V);
        for (auto& e : E) G[e[0]].push_back(e[1]), I[e[1]]++;
        queue<int> Q; for (int i = 0; i < V; i++) if (!I[i]) Q.push(i);
        vector<int> T, dp(V); dp[D] = 1;
        while (!Q.empty()) {
            int u = Q.front(); Q.pop(); T.push_back(u);
            for (int v : G[u]) if (--I[v] == 0) Q.push(v);
        }
        for (int i = V - 1; i >= 0; i--)
            for (int v : G[T[i]]) dp[T[i]] += dp[v];
        return dp[S];
    }
};
```

## Code (Java)

```java
class Solution {
    public int countPaths(int[][] E, int V, int S, int D) {
        List<List<Integer>> G = new ArrayList<>();
        int[] I = new int[V], dp = new int[V];
        for (int i = 0; i < V; i++) G.add(new ArrayList<>());
        for (int[] e : E) {
            G.get(e[0]).add(e[1]);
            I[e[1]]++;
        }
        Queue<Integer> Q = new ArrayDeque<>();
        for (int i = 0; i < V; i++) if (I[i] == 0) Q.add(i);
        List<Integer> T = new ArrayList<>();
        while (!Q.isEmpty()) {
            int u = Q.poll(); T.add(u);
            for (int v : G.get(u)) if (--I[v] == 0) Q.add(v);
        }
        dp[D] = 1;
        for (int i = V - 1; i >= 0; i--)
            for (int v : G.get(T.get(i))) dp[T.get(i)] += dp[v];
        return dp[S];
    }
}
```

## Code (Python)

```python
class Solution:
    def countPaths(self, E, V, S, D):
        from collections import defaultdict, deque
        G = defaultdict(list); I = [0] * V
        for u, v in E: G[u].append(v); I[v] += 1
        Q = deque(i for i in range(V) if I[i] == 0)
        T, dp = [], [0] * V; dp[D] = 1
        while Q:
            u = Q.popleft(); T.append(u)
            for v in G[u]:
                I[v] -= 1
                if I[v] == 0: Q.append(v)
        for u in reversed(T):
            for v in G[u]: dp[u] += dp[v]
        return dp[S]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
