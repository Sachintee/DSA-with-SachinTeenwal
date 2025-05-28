--- ❤️ ---

# 🚀 _Day 148. Maximize the Number of Target Nodes After Connecting Trees I_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/maximize-the-number-of-target-nodes-after-connecting-trees-i/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    vector<int> maxTargetNodes(vector<vector<int>>& edges1, vector<vector<int>>& edges2, int k) {
        auto g2 = build(edges2);
        int m = edges2.size() + 1;
        int t = 0;
        for (int i = 0; i < m; ++i) {
            t = max(t, dfs(g2, i, -1, k - 1));
        }

        auto g1 = build(edges1);
        int n = edges1.size() + 1;

        vector<int> ans(n, t);
        for (int i = 0; i < n; ++i) {
            ans[i] += dfs(g1, i, -1, k);
        }

        return ans;
    }

private:
    vector<vector<int>> build(const vector<vector<int>>& edges) {
        int n = edges.size() + 1;
        vector<vector<int>> g(n);
        for (const auto& e : edges) {
            int a = e[0], b = e[1];
            g[a].push_back(b);
            g[b].push_back(a);
        }
        return g;
    }

    int dfs(const vector<vector<int>>& g, int a, int fa, int d) {
        if (d < 0) {
            return 0;
        }
        int cnt = 1;
        for (int b : g[a]) {
            if (b != fa) {
                cnt += dfs(g, b, a, d - 1);
            }
        }
        return cnt;
    }
};
```

## Code (Java)

```java
class Solution {
    public int[] maxTargetNodes(int[][] edges1, int[][] edges2, int k) {
        var g2 = build(edges2);
        int m = edges2.length + 1;
        int t = 0;
        for (int i = 0; i < m; ++i) {
            t = Math.max(t, dfs(g2, i, -1, k - 1));
        }
        var g1 = build(edges1);
        int n = edges1.length + 1;
        int[] ans = new int[n];
        Arrays.fill(ans, t);
        for (int i = 0; i < n; ++i) {
            ans[i] += dfs(g1, i, -1, k);
        }
        return ans;
    }

    private List<Integer>[] build(int[][] edges) {
        int n = edges.length + 1;
        List<Integer>[] g = new List[n];
        Arrays.setAll(g, i -> new ArrayList<>());
        for (var e : edges) {
            int a = e[0], b = e[1];
            g[a].add(b);
            g[b].add(a);
        }
        return g;
    }

    private int dfs(List<Integer>[] g, int a, int fa, int d) {
        if (d < 0) {
            return 0;
        }
        int cnt = 1;
        for (int b : g[a]) {
            if (b != fa) {
                cnt += dfs(g, b, a, d - 1);
            }
        }
        return cnt;
    }
}
```

## Code (Python)

```python
class Solution:
    def maxTargetNodes(
        self, edges1: List[List[int]], edges2: List[List[int]], k: int
    ) -> List[int]:
        def build(edges: List[List[int]]) -> List[List[int]]:
            n = len(edges) + 1
            g = [[] for _ in range(n)]
            for a, b in edges:
                g[a].append(b)
                g[b].append(a)
            return g

        def dfs(g: List[List[int]], a: int, fa: int, d: int) -> int:
            if d < 0:
                return 0
            cnt = 1
            for b in g[a]:
                if b != fa:
                    cnt += dfs(g, b, a, d - 1)
            return cnt

        g2 = build(edges2)
        m = len(edges2) + 1
        t = max(dfs(g2, i, -1, k - 1) for i in range(m))
        g1 = build(edges1)
        n = len(edges1) + 1
        return [dfs(g1, i, -1, k) + t for i in range(n)]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
