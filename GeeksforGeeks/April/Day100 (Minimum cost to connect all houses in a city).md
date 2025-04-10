---
Difficulty: Medium
Source: 160 Days of Problem Solving
Tags:
  - Graph
---

# 🚀 _Day 100. Minimum cost to connect all houses in a city_ 🧠

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/graph-gfg-160/problem/minimum-cost-to-connect-all-houses-in-a-city)  


## 💡 **Problem Description:**

Given a **2D array `houses[][]`** of size `n`, where each subarray contains the `(x, y)` coordinates of a house, the goal is to **connect all houses** such that:


## Code(C++)
```cpp
class Solution {
  public:
    int minCost(vector<vector<int>>& a) {
        int n = a.size(), ans = 0, u = 0;
        vector<bool> vis(n);
        vector<int> d(n, 1e9);
        d[0] = 0;
        for (int i = 0; i < n; ++i) {
            int m = 1e9, idx = -1;
            for (int j = 0; j < n; ++j)
                if (!vis[j] && d[j] < m) m = d[j], idx = j;
            vis[idx] = 1;
            ans += m;
            for (int j = 0; j < n; ++j)
                if (!vis[j])
                    d[j] = min(d[j], abs(a[idx][0] - a[j][0]) + abs(a[idx][1] - a[j][1]));
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int minCost(int[][] a) {
        int n = a.length, ans = 0;
        boolean[] vis = new boolean[n];
        int[] d = new int[n];
        Arrays.fill(d, Integer.MAX_VALUE);
        d[0] = 0;
        for (int i = 0; i < n; i++) {
            int m = Integer.MAX_VALUE, u = -1;
            for (int j = 0; j < n; j++)
                if (!vis[j] && d[j] < m) {
                    m = d[j];
                    u = j;
                }
            vis[u] = true;
            ans += m;
            for (int j = 0; j < n; j++)
                if (!vis[j])
                    d[j] = Math.min(d[j], Math.abs(a[u][0] - a[j][0]) + Math.abs(a[u][1] - a[j][1]));
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def minCost(self, a):
        n, ans = len(a), 0
        vis = [0]*n
        d = [float('inf')]*n
        d[0] = 0
        for _ in range(n):
            m, u = float('inf'), -1
            for i in range(n):
                if not vis[i] and d[i] < m:
                    m, u = d[i], i
            vis[u] = 1
            ans += m
            for v in range(n):
                if not vis[v]:
                    d[v] = min(d[v], abs(a[u][0] - a[v][0]) + abs(a[u][1] - a[v][1]))
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
