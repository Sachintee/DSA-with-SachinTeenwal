---
Difficulty: Easy  
Source: 160 Days of Problem Solving  
Tags:
  - Greedy
  - BFS
---

# 🚀 _Day 92. BFS of Graph_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/graph-gfg-160/problem/bfs-traversal-of-graph)

## 💡 **Problem Description:** 

Given a **connected undirected graph** represented by a **2D adjacency list `adj[][]`**, where `adj[i]` represents the list of vertices connected to vertex `i`.  
Perform a **Breadth First Search (BFS) traversal** starting from **vertex 0**, visiting vertices from left to right as per the given adjacency list.  

## Code(C++)
```cpp
class Solution {
  public:
    vector<int> bfs(vector<vector<int>>& adj) {
        int V = adj.size();
        vector<int> res;
        vector<bool> vis(V, false);
        queue<int> q;
        
        q.push(0);
        vis[0] = true;
        
        while (!q.empty()) {
            int v = q.front();
            q.pop();
            res.push_back(v);
            
            for (int u : adj[v]) {
                if (!vis[u]) {
                    vis[u] = true;
                    q.push(u);
                }
            }
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<Integer> bfs(ArrayList<ArrayList<Integer>> adj) {
        ArrayList<Integer> r = new ArrayList<>();
        boolean[] v = new boolean[adj.size()];
        Queue<Integer> q = new LinkedList<>();
        q.add(0);
        v[0] = true;
        
        while (!q.isEmpty()) {
            int i = q.poll();
            r.add(i);
            for (int j : adj.get(i)) {
                if (!v[j]) {
                    v[j] = true;
                    q.add(j);
                }
            }
        }
        return r;
    }
}
```

## Code (Python)

```python
from collections import deque

class Solution:
    def bfs(self, adj):
        r, v = [], [False] * len(adj)
        q = deque([0])
        v[0] = True
        while q:
            i = q.popleft()
            r.append(i)
            for j in adj[i]:
                if not v[j]:
                    v[j] = True
                    q.append(j)
        return r
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
