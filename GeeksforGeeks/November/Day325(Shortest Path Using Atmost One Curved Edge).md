---
title: "🛤️ Shortest Path Using At Most One Curved Edge | GFG Solution 🔍"
keywords🏷️: ["🛤️ shortest path", "🔍 Dijkstra's algorithm", "📍 state tracking", "📈 priority queue", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Shortest Path Using At Most One Curved Edge problem: find minimum path length using Dijkstra with state tracking for curved edge usage. 🚀"
date: 📅 2025-11-21
---

# *325. Shortest Path Using At Most One Curved Edge*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/shortest-path-using-atmost-one-curved-edge--170647/1)

## **🧩 Problem Description**

You are given an undirected, connected graph with `V` vertices numbered from `0` to `V-1` and `E` double-edges. Each double-edge connects vertices `x` and `y` with two options:
- A **straight edge** with weight `w1`
- A **curved edge** with weight `w2`

Your task is to find the **shortest path** from vertex `a` to vertex `b` such that you can use **at most one curved edge** in the entire path. If no such path exists, return `-1`.


## Code(C++)
```cpp
class Solution {
public:
    int shortestPath(int V, int a, int b, vector<vector<int>> &edges) {
        vector<vector<pair<int,pair<int,int>>>> g(V);
        for(auto &e:edges){
            g[e[0]].push_back({e[1],{e[2],e[3]}});
            g[e[1]].push_back({e[0],{e[2],e[3]}});
        }
        vector<vector<int>> d(V,vector<int>(2,1e9));
        priority_queue<array<int,3>,vector<array<int,3>>,greater<>> pq;
        d[a][0]=0;
        pq.push({0,a,0});
        while(!pq.empty()){
            auto[dist,u,c]=pq.top();pq.pop();
            if(dist>d[u][c])continue;
            for(auto[v,w]:g[u]){
                if(d[v][c]>dist+w.first){
                    d[v][c]=dist+w.first;
                    pq.push({d[v][c],v,c});
                }
                if(!c&&d[v][1]>dist+w.second){
                    d[v][1]=dist+w.second;
                    pq.push({d[v][1],v,1});
                }
            }
        }
        int res=min(d[b][0],d[b][1]);
        return res>=1e9?-1:res;
    }
};
```

## Code (Java)

```java
class Solution {
    public int shortestPath(int V, int a, int b, int[][] edges) {
        List<List<int[]>> g=new ArrayList<>();
        for(int i=0;i<V;i++)g.add(new ArrayList<>());
        for(int[] e:edges){
            g.get(e[0]).add(new int[]{e[1],e[2],e[3]});
            g.get(e[1]).add(new int[]{e[0],e[2],e[3]});
        }
        int[][] d=new int[V][2];
        for(int[] r:d)Arrays.fill(r,1000000000);
        PriorityQueue<int[]> pq=new PriorityQueue<>((x,y)->x[0]-y[0]);
        d[a][0]=0;
        pq.offer(new int[]{0,a,0});
        while(!pq.isEmpty()){
            int[] cur=pq.poll();
            int dist=cur[0],u=cur[1],c=cur[2];
            if(dist>d[u][c])continue;
            for(int[] nxt:g.get(u)){
                int v=nxt[0],w1=nxt[1],w2=nxt[2];
                if(d[v][c]>dist+w1){
                    d[v][c]=dist+w1;
                    pq.offer(new int[]{d[v][c],v,c});
                }
                if(c==0&&d[v][1]>dist+w2){
                    d[v][1]=dist+w2;
                    pq.offer(new int[]{d[v][1],v,1});
                }
            }
        }
        int res=Math.min(d[b][0],d[b][1]);
        return res>=1000000000?-1:res;
    }
}
```

## Code (Python)

```python
class Solution:
    def shortestPath(self, V, a, b, edges):
        from heapq import heappush,heappop
        g=[[] for _ in range(V)]
        for u,v,w1,w2 in edges:
            g[u].append((v,w1,w2))
            g[v].append((u,w1,w2))
        d=[[float('inf')]*2 for _ in range(V)]
        d[a][0]=0
        pq=[(0,a,0)]
        while pq:
            dist,u,c=heappop(pq)
            if dist>d[u][c]:continue
            for v,w1,w2 in g[u]:
                if d[v][c]>dist+w1:
                    d[v][c]=dist+w1
                    heappush(pq,(d[v][c],v,c))
                if not c and d[v][1]>dist+w2:
                    d[v][1]=dist+w2
                    heappush(pq,(d[v][1],v,1))
        res=min(d[b][0],d[b][1])
        return -1 if res==float('inf') else res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
