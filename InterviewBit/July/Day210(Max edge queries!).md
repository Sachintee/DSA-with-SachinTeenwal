--- ❤️ ---

# 🚀 _Day 210. Max edge queries!_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/max-edge-queries/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <bits/stdc++.h>
using namespace std;

const int MAXN = 100005;
const int LOG = 17;

vector<pair<int, int>> tree[MAXN];
int up[MAXN][LOG];        // 2^i-th ancestor
int maxEdge[MAXN][LOG];   // max edge weight to 2^i-th ancestor
int depth[MAXN];

void dfs(int node, int parent, int weight) {
    up[node][0] = parent;
    maxEdge[node][0] = weight;

    for (int i = 1; i < LOG; i++) {
        if (up[node][i-1] != -1) {
            up[node][i] = up[up[node][i-1]][i-1];
            maxEdge[node][i] = max(maxEdge[node][i-1], maxEdge[up[node][i-1]][i-1]);
        }
    }

    for (auto [child, w] : tree[node]) {
        if (child != parent) {
            depth[child] = depth[node] + 1;
            dfs(child, node, w);
        }
    }
}

int getMaxEdge(int u, int v) {
    if (depth[u] < depth[v])
        swap(u, v);

    int maxW = 0;

    for (int i = LOG - 1; i >= 0; i--) {
        if (up[u][i] != -1 && depth[up[u][i]] >= depth[v]) {
            maxW = max(maxW, maxEdge[u][i]);
            u = up[u][i];
        }
    }

    if (u == v) return maxW;

    for (int i = LOG - 1; i >= 0; i--) {
        if (up[u][i] != -1 && up[u][i] != up[v][i]) {
            maxW = max({maxW, maxEdge[u][i], maxEdge[v][i]});
            u = up[u][i];
            v = up[v][i];
        }
    }

    return max({maxW, maxEdge[u][0], maxEdge[v][0]});
}

vector<int> solve(vector<vector<int>> &A, vector<vector<int>> &B) {
    int n = A.size() + 1;

    for (int i = 0; i <= n; i++) {
        tree[i].clear();
        for (int j = 0; j < LOG; j++) {
            up[i][j] = -1;
            maxEdge[i][j] = 0;
        }
    }

    for (auto &e : A) {
        int u = e[0], v = e[1], w = e[2];
        tree[u].emplace_back(v, w);
        tree[v].emplace_back(u, w);
    }

    depth[1] = 0;
    dfs(1, -1, 0);

    vector<int> res;
    for (auto &q : B) {
        res.push_back(getMaxEdge(q[0], q[1]));
    }

    return res;
}

```

## Code (Java)

```java
import java.util.*;

public class Solution {
    static final int MAXN = 100005;
    static final int LOG = 17;

    static List<int[]>[] tree = new ArrayList[MAXN];
    static int[][] up = new int[MAXN][LOG];
    static int[][] maxEdge = new int[MAXN][LOG];
    static int[] depth = new int[MAXN];

    public static void dfs(int node, int parent, int weight) {
        up[node][0] = parent;
        maxEdge[node][0] = weight;

        for (int i = 1; i < LOG; i++) {
            if (up[node][i - 1] != -1) {
                up[node][i] = up[up[node][i - 1]][i - 1];
                maxEdge[node][i] = Math.max(maxEdge[node][i - 1], maxEdge[up[node][i - 1]][i - 1]);
            }
        }

        for (int[] neighbor : tree[node]) {
            int child = neighbor[0];
            int w = neighbor[1];
            if (child != parent) {
                depth[child] = depth[node] + 1;
                dfs(child, node, w);
            }
        }
    }

    public static int getMaxEdge(int u, int v) {
        if (depth[u] < depth[v]) {
            int tmp = u;
            u = v;
            v = tmp;
        }

        int maxW = 0;
        for (int i = LOG - 1; i >= 0; i--) {
            if (up[u][i] != -1 && depth[up[u][i]] >= depth[v]) {
                maxW = Math.max(maxW, maxEdge[u][i]);
                u = up[u][i];
            }
        }

        if (u == v) return maxW;

        for (int i = LOG - 1; i >= 0; i--) {
            if (up[u][i] != -1 && up[u][i] != up[v][i]) {
                maxW = Math.max(maxW, Math.max(maxEdge[u][i], maxEdge[v][i]));
                u = up[u][i];
                v = up[v][i];
            }
        }

        return Math.max(maxW, Math.max(maxEdge[u][0], maxEdge[v][0]));
    }

    public static List<Integer> solve(int[][] A, int[][] B) {
        int n = A.length + 1;

        // initialize
        for (int i = 0; i <= n; i++) {
            tree[i] = new ArrayList<>();
            Arrays.fill(up[i], -1);
            Arrays.fill(maxEdge[i], 0);
        }

        for (int[] edge : A) {
            int u = edge[0], v = edge[1], w = edge[2];
            tree[u].add(new int[]{v, w});
            tree[v].add(new int[]{u, w});
        }

        depth[1] = 0;
        dfs(1, -1, 0);

        List<Integer> res = new ArrayList<>();
        for (int[] query : B) {
            res.add(getMaxEdge(query[0], query[1]));
        }

        return res;
    }

    // For testing
    public static void main(String[] args) {
        int[][] A = {
            {1, 2, 11},
            {1, 3, 1},
            {2, 4, 12},
            {2, 5, 100}
        };
        int[][] B = {
            {3, 5},
            {2, 3}
        };

        List<Integer> result = solve(A, B);
        for (int val : result) {
            System.out.print(val + " ");
        }
        System.out.println();
    }
}

```

## Code (Python)

```python
import sys
sys.setrecursionlimit(1 << 25)

class Solution:
    def solve(self, A, B):
        from math import log2, ceil
        n = len(A) + 1
        LOG = ceil(log2(n)) + 1

        # Tree
        tree = [[] for _ in range(n + 1)]
        for u, v, w in A:
            tree[u].append((v, w))
            tree[v].append((u, w))

        # Binary Lifting
        up = [[-1] * LOG for _ in range(n + 1)]        # up[v][j]: 2^j-th ancestor of v
        maxEdge = [[0] * LOG for _ in range(n + 1)]    # maxEdge[v][j]: max weight on path to 2^j-th ancestor
        depth = [0] * (n + 1)

        def dfs(u, p):
            for v, w in tree[u]:
                if v != p:
                    depth[v] = depth[u] + 1
                    up[v][0] = u
                    maxEdge[v][0] = w
                    for j in range(1, LOG):
                        if up[v][j-1] != -1:
                            up[v][j] = up[up[v][j-1]][j-1]
                            maxEdge[v][j] = max(maxEdge[v][j-1], maxEdge[up[v][j-1]][j-1])
                    dfs(v, u)

        dfs(1, -1)

        def query(u, v):
            if depth[u] < depth[v]:
                u, v = v, u

            max_w = 0

            # Lift u to depth of v
            for j in reversed(range(LOG)):
                if up[u][j] != -1 and depth[up[u][j]] >= depth[v]:
                    max_w = max(max_w, maxEdge[u][j])
                    u = up[u][j]

            if u == v:
                return max_w

            # Lift both u and v
            for j in reversed(range(LOG)):
                if up[u][j] != -1 and up[u][j] != up[v][j]:
                    max_w = max(max_w, maxEdge[u][j], maxEdge[v][j])
                    u = up[u][j]
                    v = up[v][j]

            # One step above LCA
            max_w = max(max_w, maxEdge[u][0], maxEdge[v][0])
            return max_w

        return [query(u, v) for u, v in B]

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
