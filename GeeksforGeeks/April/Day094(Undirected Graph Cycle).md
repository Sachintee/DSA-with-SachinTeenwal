---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Graph
  - Union-Find
  - DFS
---

# 🚀 _Day 94. Undirected Graph Cycle_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/graph-gfg-160/problem/detect-cycle-in-an-undirected-graph)  


## 💡 **Problem Description:** 

Given an **undirected graph** with `V` vertices and `E` edges, represented as a 2D vector `edges[][]`, where each entry `edges[i] = [u, v]` denotes an edge between vertices `u` and `v`, determine whether the graph contains a **cycle** or not.  


## Code(C++)
```cpp
class Solution {
public:
    bool isCycle(int V, vector<vector<int>>& edges) {
        vector<int> p(V, -1);
        function<int(int)> f = [&](int x){ return p[x] < 0 ? x : p[x] = f(p[x]); };
        for(auto &e : edges){
            int a = f(e[0]), b = f(e[1]);
            if(a == b) return true;
            if(p[a] > p[b]) swap(a, b);
            p[a] += p[b]; p[b] = a;
        }
        return false;
    }
};
```

## Code (Java)

```java
class Solution {
    public boolean isCycle(int V, int[][] edges) {
        int[] p = new int[V];
        Arrays.fill(p, -1);
        for (int[] e : edges) {
            int a = f(p, e[0]), b = f(p, e[1]);
            if (a == b) return true;
            if (p[a] > p[b]) { int t = a; a = b; b = t; }
            p[a] += p[b]; p[b] = a;
        }
        return false;
    }
    int f(int[] p, int x) {
        return p[x] < 0 ? x : (p[x] = f(p, p[x]));
    }
}
```

## Code (Python)

```python
class Solution:
    def isCycle(self, V, edges):
        p = [-1]*V
        def f(x): return x if p[x]<0 else f(p[x])
        for u,v in edges:
            a, b = f(u), f(v)
            if a == b: return True
            if p[a] > p[b]: a,b = b,a
            p[a] += p[b]; p[b] = a
        return False
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
