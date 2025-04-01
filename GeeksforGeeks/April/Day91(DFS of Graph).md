---
Difficulty: Easy  
Source: 160 Days of Problem Solving  
Tags:
  - Greedy
  - DFS
---

# 🚀 _Day 91. DFS of Graph_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/graph-gfg-160/problem/depth-first-traversal-for-a-graph)  

## 💡 **Problem Description:** 

Given a **connected undirected graph** represented by a **2D adjacency list `adj[][]`**, where `adj[i]` represents the list of vertices connected to vertex `i`.  
Perform a **Depth First Search (DFS) traversal** starting from **vertex 0**, visiting vertices from left to right as per the given adjacency list.  


## Code(C++)
```cpp
class Solution {
  public:
    vector<int> dfs(vector<vector<int>>& adj) {
        int V = adj.size();
        vector<int> res, vis(V, 0);
        function<void(int)> traverse = [&](int v) {
            vis[v] = 1;
            res.push_back(v);
            for (int u : adj[v])
                if (!vis[u]) traverse(u);
        };
        for (int i = 0; i < V; i++)
            if (!vis[i]) traverse(i);
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<Integer> dfs(ArrayList<ArrayList<Integer>> adj) {
        ArrayList<Integer> r = new ArrayList<>();
        boolean[] v = new boolean[adj.size()];
        for (int i = 0; i < adj.size(); i++) if (!v[i]) go(i, adj, v, r);
        return r;
    }
    void go(int i, ArrayList<ArrayList<Integer>> a, boolean[] v, ArrayList<Integer> r) {
        v[i] = true;
        r.add(i);
        for (int j : a.get(i)) if (!v[j]) go(j, a, v, r);
    }
}
```

## Code (Python)

```python
class Solution:
    def dfs(self, adj):
        r, v = [], [False] * len(adj)
        def go(i):
            v[i] = True
            r.append(i)
            for j in adj[i]:
                if not v[j]:
                    go(j)
        for i in range(len(adj)):
            if not v[i]:
                go(i)
        return r

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
