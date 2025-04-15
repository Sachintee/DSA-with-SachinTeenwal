---
Difficulty: Medium
Source: 160 Days of Problem Solving
Tags:
  - Graph
  - Dynamic Programming
---

# 🚀 _Day 105. Bellman-Ford_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/graph-gfg-160/problem/distance-from-the-source-bellman-ford-algorithm)  



## 💡 **Problem Description:**

Given a **weighted graph** with `V` vertices (numbered from `0` to `V-1`) and a list of `E` edges, where each edge is represented as a triplet `[u, v, w]` denoting a **directed edge from `u` to `v`** with weight `w`.

Also given a source vertex `src`.  
Your task is to compute the **shortest distance from the source to all other vertices** using the **Bellman-Ford algorithm**.

- If a vertex is unreachable from the source, mark its distance as **1e8**.
- If the graph contains a **negative weight cycle**, return `[-1]`.


## Code(C++)
```cpp
//Standard Bellman-Ford Algorithm
class Solution {
  public:
    vector<int> bellmanFord(int V, vector<vector<int>>& edges, int src) {
        vector<int> dist(V, 1e8);
        dist[src] = 0;
        for (int i = 0; i < V - 1; ++i)
            for (auto& e : edges)
                if (dist[e[0]] != 1e8 && dist[e[0]] + e[2] < dist[e[1]])
                    dist[e[1]] = dist[e[0]] + e[2];
        for (auto& e : edges)
            if (dist[e[0]] != 1e8 && dist[e[0]] + e[2] < dist[e[1]])
                return {-1};
        return dist;
    }
};
```

## Code (Java)

```java
class Solution {
    public int[] bellmanFord(int V, int[][] edges, int src) {
        int[] dist = new int[V];
        Arrays.fill(dist, (int)1e8);
        dist[src] = 0;
        for (int i = 0; i < V - 1; i++)
            for (int[] e : edges)
                if (dist[e[0]] < 1e8 && dist[e[0]] + e[2] < dist[e[1]])
                    dist[e[1]] = dist[e[0]] + e[2];
        for (int[] e : edges)
            if (dist[e[0]] < 1e8 && dist[e[0]] + e[2] < dist[e[1]])
                return new int[]{-1};
        return dist;
    }
}
```

## Code (Python)

```python
class Solution:
    def bellmanFord(self, V, edges, src):
        dist = [int(1e8)] * V
        dist[src] = 0
        for _ in range(V - 1):
            for u, v, w in edges:
                if dist[u] < 1e8 and dist[u] + w < dist[v]:
                    dist[v] = dist[u] + w
        for u, v, w in edges:
            if dist[u] < 1e8 and dist[u] + w < dist[v]:
                return [-1]
        return dist
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
