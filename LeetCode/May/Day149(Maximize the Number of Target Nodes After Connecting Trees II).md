--- ❤️ ---

# 🚀 _Day 149. Maximize the Number of Target Nodes After Connecting Trees II_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/maximize-the-number-of-target-nodes-after-connecting-trees-ii/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    vector<int> maxTargetNodes(vector<vector<int>>& edges1, vector<vector<int>>& edges2) {
        auto g1 = build(edges1);
        auto g2 = build(edges2);
        int n = g1.size(), m = g2.size();
        vector<int> c1(n, 0), c2(m, 0);
        vector<int> cnt1(2, 0), cnt2(2, 0);

        dfs(g2, 0, -1, c2, 0, cnt2);
        dfs(g1, 0, -1, c1, 0, cnt1);

        int t = max(cnt2[0], cnt2[1]);
        vector<int> ans(n);
        for (int i = 0; i < n; ++i) {
            ans[i] = t + cnt1[c1[i]];
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

    void dfs(const vector<vector<int>>& g, int a, int fa, vector<int>& c, int d, vector<int>& cnt) {
        c[a] = d;
        cnt[d]++;
        for (int b : g[a]) {
            if (b != fa) {
                dfs(g, b, a, c, d ^ 1, cnt);
            }
        }
    }
};
```

## Code (Java)

```java
class Solution {
    public int[] maxTargetNodes(int[][] edges1, int[][] edges2) {
        var g1 = build(edges1);
        var g2 = build(edges2);
        int n = g1.length, m = g2.length;
        int[] c1 = new int[n];
        int[] c2 = new int[m];
        int[] cnt1 = new int[2];
        int[] cnt2 = new int[2];
        dfs(g2, 0, -1, c2, 0, cnt2);
        dfs(g1, 0, -1, c1, 0, cnt1);
        int t = Math.max(cnt2[0], cnt2[1]);
        int[] ans = new int[n];
        for (int i = 0; i < n; ++i) {
            ans[i] = t + cnt1[c1[i]];
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

    private void dfs(List<Integer>[] g, int a, int fa, int[] c, int d, int[] cnt) {
        c[a] = d;
        cnt[d]++;
        for (int b : g[a]) {
            if (b != fa) {
                dfs(g, b, a, c, d ^ 1, cnt);
            }
        }
    }
}
```

## Code (Python)

```python
class Solution:
    def maxTargetNodes(
        self, edges1: List[List[int]], edges2: List[List[int]]
    ) -> List[int]:
        def build(edges: List[List[int]]) -> List[List[int]]:
            n = len(edges) + 1
            g = [[] for _ in range(n)]
            for a, b in edges:
                g[a].append(b)
                g[b].append(a)
            return g

        def dfs(
            g: List[List[int]], a: int, fa: int, c: List[int], d: int, cnt: List[int]
        ):
            c[a] = d
            cnt[d] += 1
            for b in g[a]:
                if b != fa:
                    dfs(g, b, a, c, d ^ 1, cnt)

        g1 = build(edges1)
        g2 = build(edges2)
        n, m = len(g1), len(g2)
        c1 = [0] * n
        c2 = [0] * m
        cnt1 = [0, 0]
        cnt2 = [0, 0]
        dfs(g2, 0, -1, c2, 0, cnt2)
        dfs(g1, 0, -1, c1, 0, cnt1)
        t = max(cnt2)
        return [t + cnt1[c1[i]] for i in range(n)]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
