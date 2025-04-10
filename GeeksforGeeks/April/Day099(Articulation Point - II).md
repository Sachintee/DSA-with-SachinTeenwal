--- ❤️ ---

# 🚀 _Day 99. Articulation Point - II_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/graph-gfg-160/problem/articulation-point2616)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
  public:
    void dfs(int u, int parent, vector<int> adj[], vector<int>& tin, vector<int>& low,
             vector<bool>& vis, vector<bool>& isArticulation, int& timer) {
        vis[u] = true;
        tin[u] = low[u] = timer++;
        int children = 0;
        for (int v : adj[u]) {
            if (v == parent) continue;
            if (!vis[v]) {
                dfs(v, u, adj, tin, low, vis, isArticulation, timer);
                low[u] = min(low[u], low[v]);
                if (low[v] >= tin[u] && parent != -1) {
                    isArticulation[u] = true;
                }
                ++children;
            } else {
                low[u] = min(low[u], tin[v]);
            }
        }
        if (parent == -1 && children > 1) {
            isArticulation[u] = true;
        }
    }
    vector<int> articulationPoints(int V, vector<vector<int>>& edges) {
        vector<int> adj[V];
        for (auto& edge : edges) {
            int u = edge[0], v = edge[1];
            adj[u].push_back(v);
            adj[v].push_back(u);
        }
        vector<int> tin(V, -1), low(V, -1);
        vector<bool> vis(V, false), isArticulation(V, false);
        int timer = 0;
        for (int i = 0; i < V; i++) {
            if (!vis[i]) {
                dfs(i, -1, adj, tin, low, vis, isArticulation, timer);
            }
        }
        vector<int> result;
        for (int i = 0; i < V; i++) {
            if (isArticulation[i]) result.push_back(i);
        }
        if (result.empty()) return {-1};
        return result;
    }
};
```

## Code (Java)

```java
import java.util.*;

class Solution {
    private int timer = 0;

    public List<Integer> articulationPoints(int V, List<List<Integer>> edges) {
        List<Integer>[] adj = new ArrayList[V];
        for (int i = 0; i < V; i++) {
            adj[i] = new ArrayList<>();
        }
        for (List<Integer> edge : edges) {
            int u = edge.get(0);
            int v = edge.get(1);
            adj[u].add(v);
            adj[v].add(u);
        }

        int[] tin = new int[V];
        int[] low = new int[V];
        boolean[] vis = new boolean[V];
        boolean[] isArticulation = new boolean[V];
        Arrays.fill(tin, -1);
        Arrays.fill(low, -1);

        for (int i = 0; i < V; i++) {
            if (!vis[i]) {
                dfs(i, -1, adj, tin, low, vis, isArticulation);
            }
        }

        List<Integer> result = new ArrayList<>();
        for (int i = 0; i < V; i++) {
            if (isArticulation[i]) {
                result.add(i);
            }
        }
        if (result.isEmpty()) {
            result.add(-1);
        }
        return result;
    }

    private void dfs(int u, int parent, List<Integer>[] adj, int[] tin, int[] low, boolean[] vis, boolean[] isArticulation) {
        vis[u] = true;
        tin[u] = low[u] = timer++;
        int children = 0;
        for (int v : adj[u]) {
            if (v == parent) continue;
            if (!vis[v]) {
                dfs(v, u, adj, tin, low, vis, isArticulation);
                low[u] = Math.min(low[u], low[v]);
                if (low[v] >= tin[u] && parent != -1) {
                    isArticulation[u] = true;
                }
                children++;
            } else {
                low[u] = Math.min(low[u], tin[v]);
            }
        }
        if (parent == -1 && children > 1) {
            isArticulation[u] = true;
        }
    }
}
```

## Code (Python)

```python
class Solution:
    def articulationPoints(self, V, edges):
        from collections import defaultdict

        adj = defaultdict(list)
        for u, v in edges:
            adj[u].append(v)
            adj[v].append(u)

        tin = [-1] * V
        low = [-1] * V
        vis = [False] * V
        is_articulation = [False] * V
        timer = 0

        def dfs(u, parent):
            nonlocal timer
            vis[u] = True
            tin[u] = low[u] = timer
            timer += 1
            children = 0
            for v in adj[u]:
                if v == parent:
                    continue
                if not vis[v]:
                    dfs(v, u)
                    low[u] = min(low[u], low[v])
                    if low[v] >= tin[u] and parent != -1:
                        is_articulation[u] = True
                    children += 1
                else:
                    low[u] = min(low[u], tin[v])
            if parent == -1 and children > 1:
                is_articulation[u] = True

        for i in range(V):
            if not vis[i]:
                dfs(i, -1)

        result = [i for i in range(V) if is_articulation[i]]
        return result if result else [-1]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
