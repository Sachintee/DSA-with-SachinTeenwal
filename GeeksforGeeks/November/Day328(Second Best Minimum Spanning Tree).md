---
title: "🔢 Second Best Minimum Spanning Tree | GFG Solution 🔍"
keywords🏷️: ["🔢 second MST", "🌲 spanning tree", "🔍 Kruskal's algorithm", "📊 union-find", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Second Best Minimum Spanning Tree problem: find the second minimum weight spanning tree using MST edge removal technique with Kruskal's algorithm and union-find. 🚀"
date: 📅 2025-11-24
---

# *328. Second Best Minimum Spanning Tree*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/second-best-minimum-spanning-tree/1)

## **🧩 Problem Description**

You are given an undirected graph with `V` vertices numbered from `0` to `V-1` and `E` edges. Each edge is represented as `[u, v, w]`, where `u` and `v` are connected vertices with weight `w`. Your task is to find the weight of the **second best minimum spanning tree** of the given graph.

A second best MST is defined as a minimum-weight spanning tree whose total weight is **strictly greater** than the weight of the minimum spanning tree (MST). If no such second best MST exists, return `-1`.


## Code(C++)
```cpp
class Solution {
public:
    int secondMST(int V, vector<vector<int>>& edges) {
        sort(edges.begin(), edges.end(), [](auto& a, auto& b) { return a[2] < b[2]; });
        vector<int> p(V), r(V);
        iota(p.begin(), p.end(), 0);
        function<int(int)> find = [&](int x) { return p[x] == x ? x : p[x] = find(p[x]); };
        auto unite = [&](int a, int b) {
            a = find(a); b = find(b);
            if (a == b) return false;
            if (r[a] < r[b]) swap(a, b);
            p[b] = a;
            if (r[a] == r[b]) r[a]++;
            return true;
        };
        int mst = 0, ans = INT_MAX;
        vector<array<int, 3>> tree;
        for (auto& e : edges) {
            if (unite(e[0], e[1])) {
                mst += e[2];
                tree.push_back({e[0], e[1], e[2]});
            }
        }
        for (auto& [u, v, w] : tree) {
            fill(p.begin(), p.end(), 0);
            iota(p.begin(), p.end(), 0);
            fill(r.begin(), r.end(), 0);
            int cost = 0, cnt = 0;
            for (auto& e : edges) {
                if ((e[0] == u && e[1] == v) || (e[0] == v && e[1] == u)) continue;
                if (unite(e[0], e[1])) {
                    cost += e[2];
                    if (++cnt == V - 1) break;
                }
            }
            if (cnt == V - 1 && cost > mst) ans = min(ans, cost);
        }
        return ans == INT_MAX ? -1 : ans;
    }
};
```

## Code (Java)

```java

```

## Code (Python)

```python

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
