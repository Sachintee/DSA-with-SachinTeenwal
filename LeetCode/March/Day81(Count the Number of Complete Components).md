--- ❤️ ---

# 🚀 _Day 81. Count the Number of Complete Components_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/count-the-number-of-complete-components/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int countCompleteComponents(int n, vector<vector<int>>& edges) {
        vector<vector<int>> g(n);
        bool vis[n];
        memset(vis, false, sizeof(vis));
        for (auto& e : edges) {
            int a = e[0], b = e[1];
            g[a].push_back(b);
            g[b].push_back(a);
        }
        function<pair<int, int>(int)> dfs = [&](int i) -> pair<int, int> {
            vis[i] = true;
            int x = 1, y = g[i].size();
            for (int j : g[i]) {
                if (!vis[j]) {
                    auto [a, b] = dfs(j);
                    x += a;
                    y += b;
                }
            }
            return make_pair(x, y);
        };
        int ans = 0;
        for (int i = 0; i < n; ++i) {
            if (!vis[i]) {
                auto [a, b] = dfs(i);
                if (a * (a - 1) == b) {
                    ++ans;
                }
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    private List<Integer>[] g;
    private boolean[] vis;

    public int countCompleteComponents(int n, int[][] edges) {
        g = new List[n];
        vis = new boolean[n];
        Arrays.setAll(g, k -> new ArrayList<>());
        for (int[] e : edges) {
            int a = e[0], b = e[1];
            g[a].add(b);
            g[b].add(a);
        }
        int ans = 0;
        for (int i = 0; i < n; ++i) {
            if (!vis[i]) {
                int[] t = dfs(i);
                if (t[0] * (t[0] - 1) == t[1]) {
                    ++ans;
                }
            }
        }
        return ans;
    }

    private int[] dfs(int i) {
        vis[i] = true;
        int x = 1, y = g[i].size();
        for (int j : g[i]) {
            if (!vis[j]) {
                int[] t = dfs(j);
                x += t[0];
                y += t[1];
            }
        }
        return new int[] {x, y};
    }
}
```

## Code (Python)

```python
class Solution:
    def countCompleteComponents(self, n: int, edges: List[List[int]]) -> int:
        def dfs(i: int) -> (int, int):
            vis[i] = True
            x, y = 1, len(g[i])
            for j in g[i]:
                if not vis[j]:
                    a, b = dfs(j)
                    x += a
                    y += b
            return x, y

        g = defaultdict(list)
        for a, b in edges:
            g[a].append(b)
            g[b].append(a)
        vis = [False] * n
        ans = 0
        for i in range(n):
            if not vis[i]:
                a, b = dfs(i)
                ans += a * (a - 1) == b
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
