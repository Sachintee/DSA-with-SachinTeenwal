--- ❤️ ---

# 🚀 _Day 55.  Most Profitable Path in a Tree_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/most-profitable-path-in-a-tree/description/?envType=daily-question&envId=2025-02-24)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int mostProfitablePath(vector<vector<int>>& edges, int bob, vector<int>& amount) {
        int n = edges.size() + 1;
        vector<vector<int>> g(n);
        for (auto& e : edges) {
            int a = e[0], b = e[1];
            g[a].emplace_back(b);
            g[b].emplace_back(a);
        }
        vector<int> ts(n, n);
        function<bool(int i, int fa, int t)> dfs1 = [&](int i, int fa, int t) -> bool {
            if (i == 0) {
                ts[i] = t;
                return true;
            }
            for (int j : g[i]) {
                if (j != fa && dfs1(j, i, t + 1)) {
                    ts[j] = min(ts[j], t + 1);
                    return true;
                }
            }
            return false;
        };
        dfs1(bob, -1, 0);
        ts[bob] = 0;
        int ans = INT_MIN;
        function<void(int i, int fa, int t, int v)> dfs2 = [&](int i, int fa, int t, int v) {
            if (t == ts[i])
                v += amount[i] >> 1;
            else if (t < ts[i])
                v += amount[i];
            if (g[i].size() == 1 && g[i][0] == fa) {
                ans = max(ans, v);
                return;
            }
            for (int j : g[i])
                if (j != fa) dfs2(j, i, t + 1, v);
        };
        dfs2(0, -1, 0, 0);
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    private List<Integer>[] g;
    private int[] amount;
    private int[] ts;
    private int ans = Integer.MIN_VALUE;

    public int mostProfitablePath(int[][] edges, int bob, int[] amount) {
        int n = edges.length + 1;
        g = new List[n];
        ts = new int[n];
        this.amount = amount;
        Arrays.setAll(g, k -> new ArrayList<>());
        Arrays.fill(ts, n);
        for (var e : edges) {
            int a = e[0], b = e[1];
            g[a].add(b);
            g[b].add(a);
        }
        dfs1(bob, -1, 0);
        ts[bob] = 0;
        dfs2(0, -1, 0, 0);
        return ans;
    }

    private boolean dfs1(int i, int fa, int t) {
        if (i == 0) {
            ts[i] = Math.min(ts[i], t);
            return true;
        }
        for (int j : g[i]) {
            if (j != fa && dfs1(j, i, t + 1)) {
                ts[j] = Math.min(ts[j], t + 1);
                return true;
            }
        }
        return false;
    }

    private void dfs2(int i, int fa, int t, int v) {
        if (t == ts[i]) {
            v += amount[i] >> 1;
        } else if (t < ts[i]) {
            v += amount[i];
        }
        if (g[i].size() == 1 && g[i].get(0) == fa) {
            ans = Math.max(ans, v);
            return;
        }
        for (int j : g[i]) {
            if (j != fa) {
                dfs2(j, i, t + 1, v);
            }
        }
    }
}
```

## Code (Python)

```python
class Solution:
    def mostProfitablePath(
        self, edges: List[List[int]], bob: int, amount: List[int]
    ) -> int:
        def dfs1(i, fa, t):
            if i == 0:
                ts[i] = min(ts[i], t)
                return True
            for j in g[i]:
                if j != fa and dfs1(j, i, t + 1):
                    ts[j] = min(ts[j], t + 1)
                    return True
            return False

        def dfs2(i, fa, t, v):
            if t == ts[i]:
                v += amount[i] // 2
            elif t < ts[i]:
                v += amount[i]
            nonlocal ans
            if len(g[i]) == 1 and g[i][0] == fa:
                ans = max(ans, v)
                return
            for j in g[i]:
                if j != fa:
                    dfs2(j, i, t + 1, v)

        n = len(edges) + 1
        g = defaultdict(list)
        ts = [n] * n
        for a, b in edges:
            g[a].append(b)
            g[b].append(a)
        dfs1(bob, -1, 0)
        ts[bob] = 0
        ans = -inf
        dfs2(0, -1, 0, 0)
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
