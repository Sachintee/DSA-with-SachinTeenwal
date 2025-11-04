--- ❤️ ---

# 🚀 _Day 308. Queries On A Tree_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/queries-on-a-tree/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <bits/stdc++.h>
using namespace std;

class Solution {
public:
    vector<int> solve(vector<int>& A, vector<vector<int>>& B) {
        int N = A.size() + 1;
        vector<vector<int>> g(N + 1);
        
        // Build tree
        for (int i = 0; i < A.size(); i++) {
            int u = i + 2;
            int v = A[i];
            g[u].push_back(v);
            g[v].push_back(u);
        }
        
        // LCA preprocessing
        int LOG = ceil(log2(N)) + 1;
        vector<int> tin(N + 1), tout(N + 1), depth(N + 1);
        vector<vector<int>> parent(LOG, vector<int>(N + 1, -1));
        int timer = 0;
        
        // DFS for Euler tour and parent
        function<void(int, int, int)> dfs = [&](int u, int p, int d) {
            tin[u] = ++timer;
            depth[u] = d;
            parent[0][u] = p;
            
            for (int v : g[u]) {
                if (v != p) {
                    dfs(v, u, d + 1);
                }
            }
            tout[u] = timer;
        };
        
        dfs(1, -1, 0);
        
        // Binary lifting
        for (int k = 1; k < LOG; k++) {
            for (int i = 1; i <= N; i++) {
                if (parent[k-1][i] != -1) {
                    parent[k][i] = parent[k-1][parent[k-1][i]];
                }
            }
        }
        
        // LCA function
        auto is_ancestor = [&](int u, int v) {
            return tin[u] <= tin[v] && tout[v] <= tout[u];
        };
        
        auto lca = [&](int u, int v) {
            if (is_ancestor(u, v)) return u;
            if (is_ancestor(v, u)) return v;
            for (int k = LOG-1; k >= 0; k--) {
                if (parent[k][u] != -1 && !is_ancestor(parent[k][u], v)) {
                    u = parent[k][u];
                }
            }
            return parent[0][u];
        };
        
        // Distance function
        auto dist = [&](int u, int v) {
            int p = lca(u, v);
            return depth[u] + depth[v] - 2 * depth[p];
        };
        
        // Process queries
        map<int, vector<int>> queries;
        for (auto& q : B) {
            int qid = q[0], node = q[1];
            queries[qid].push_back(node);
        }
        
        vector<int> res;
        for (auto& [qid, nodes_vec] : queries) {
            // Remove duplicates
            unordered_set<int> s(nodes_vec.begin(), nodes_vec.end());
            vector<int> nodes(s.begin(), s.end());
            int k = nodes.size();
            
            if (k == 0) {
                res.push_back(0);
                continue;
            }
            if (k == 1) {
                res.push_back(1);
                continue;
            }
            
            // Sort by Euler tour entry time
            sort(nodes.begin(), nodes.end(), [&](int a, int b) {
                return tin[a] < tin[b];
            });
            
            int total = 0;
            for (int i = 0; i < k; i++) {
                total += dist(nodes[i], nodes[(i + 1) % k]);
            }
            int edges = total / 2;
            res.push_back(edges + 1);
        }
        
        return res;
    }
};
```

## Code (Java)

```java
import java.util.*;
import java.util.stream.Collectors;

public class Solution {
    private int timer;
    private int[] tin, tout, depth;
    private int[][] parent;
    private List<List<Integer>> graph;
    private int LOG;
    
    public int[] solve(int[] A, int[][] B) {
        int N = A.length + 1;
        
        // Build graph
        graph = new ArrayList<>();
        for (int i = 0; i <= N; i++) {
            graph.add(new ArrayList<>());
        }
        
        for (int i = 0; i < A.length; i++) {
            int u = i + 2;
            int v = A[i];
            graph.get(u).add(v);
            graph.get(v).add(u);
        }
        
        // LCA preprocessing
        LOG = (int) (Math.log(N) / Math.log(2)) + 2;
        tin = new int[N + 1];
        tout = new int[N + 1];
        depth = new int[N + 1];
        parent = new int[LOG][N + 1];
        
        for (int i = 0; i < LOG; i++) {
            Arrays.fill(parent[i], -1);
        }
        
        timer = 0;
        dfs(1, -1, 0);
        
        // Binary lifting
        for (int k = 1; k < LOG; k++) {
            for (int i = 1; i <= N; i++) {
                if (parent[k-1][i] != -1) {
                    parent[k][i] = parent[k-1][parent[k-1][i]];
                }
            }
        }
        
        // Process queries
        Map<Integer, List<Integer>> queries = new TreeMap<>();
        for (int[] q : B) {
            int qid = q[0], node = q[1];
            queries.computeIfAbsent(qid, k -> new ArrayList<>()).add(node);
        }
        
        List<Integer> result = new ArrayList<>();
        for (Map.Entry<Integer, List<Integer>> entry : queries.entrySet()) {
            List<Integer> nodesList = entry.getValue();
            Set<Integer> uniqueNodes = new HashSet<>(nodesList);
            List<Integer> nodes = new ArrayList<>(uniqueNodes);
            int k = nodes.size();
            
            if (k == 0) {
                result.add(0);
                continue;
            }
            if (k == 1) {
                result.add(1);
                continue;
            }
            
            // Sort by Euler tour entry time
            nodes.sort(Comparator.comparingInt(node -> tin[node]));
            
            int total = 0;
            for (int i = 0; i < k; i++) {
                total += dist(nodes.get(i), nodes.get((i + 1) % k));
            }
            int edges = total / 2;
            result.add(edges + 1);
        }
        
        return result.stream().mapToInt(i -> i).toArray();
    }
    
    private void dfs(int u, int p, int d) {
        tin[u] = ++timer;
        depth[u] = d;
        parent[0][u] = p;
        
        for (int v : graph.get(u)) {
            if (v != p) {
                dfs(v, u, d + 1);
            }
        }
        tout[u] = timer;
    }
    
    private boolean isAncestor(int u, int v) {
        return tin[u] <= tin[v] && tout[v] <= tout[u];
    }
    
    private int lca(int u, int v) {
        if (isAncestor(u, v)) return u;
        if (isAncestor(v, u)) return v;
        for (int k = LOG - 1; k >= 0; k--) {
            if (parent[k][u] != -1 && !isAncestor(parent[k][u], v)) {
                u = parent[k][u];
            }
        }
        return parent[0][u];
    }
    
    private int dist(int u, int v) {
        int p = lca(u, v);
        return depth[u] + depth[v] - 2 * depth[p];
    }
}
```

## Code (Python)

```python
from collections import defaultdict, deque
import sys
sys.setrecursionlimit(300000)

class Solution:
    def solve(self, A, B):
        N = len(A) + 1
        g = defaultdict(list)
        for i, p in enumerate(A):
            u = i + 2
            v = p
            g[u].append(v)
            g[v].append(u)
        
        # Euler tour and LCA prep
        LOG = (N).bit_length()
        tin = [0] * (N + 1)
        tout = [0] * (N + 1)
        depth = [0] * (N + 1)
        parent = [[-1] * (N + 1) for _ in range(LOG)]
        timer = 0
        
        stack = [(1, -1, 0, 0)]  # node, par, dep, state
        while stack:
            u, p, d, st = stack.pop()
            if st == 0:
                timer += 1
                tin[u] = timer
                depth[u] = d
                parent[0][u] = p
                # first visit
                stack.append((u, p, d, 1))
                for v in g[u]:
                    if v != p:
                        stack.append((v, u, d + 1, 0))
            else:
                tout[u] = timer
        
        # binary lifting preprocessing
        for k in range(1, LOG):
            for i in range(1, N + 1):
                if parent[k-1][i] != -1:
                    parent[k][i] = parent[k-1][parent[k-1][i]]
        
        def is_ancestor(u, v):
            return tin[u] <= tin[v] and tout[v] <= tout[u]
        
        def lca(u, v):
            if is_ancestor(u, v):
                return u
            if is_ancestor(v, u):
                return v
            for k in range(LOG-1, -1, -1):
                if parent[k][u] != -1 and not is_ancestor(parent[k][u], v):
                    u = parent[k][u]
            return parent[0][u]
        
        def dist(u, v):
            p = lca(u, v)
            return depth[u] + depth[v] - 2 * depth[p]
        
        # Organize queries
        queries = defaultdict(list)
        for qid, node in B:
            queries[qid].append(node)
        
        res = []
        for qid in sorted(queries.keys()):
            nodes = list(set(queries[qid]))  # unique nodes
            k = len(nodes)
            if k == 0:
                res.append(0)
                continue
            if k == 1:
                res.append(1)
                continue
            
            # Sort by Euler tour entry time
            nodes.sort(key=lambda x: tin[x])
            total = 0
            for i in range(k):
                total += dist(nodes[i], nodes[(i+1) % k])
            edges = total // 2
            res.append(edges + 1)
        
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
