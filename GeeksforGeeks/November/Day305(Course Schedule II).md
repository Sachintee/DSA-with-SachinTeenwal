---
title: "🎓 Course Schedule II | GFG Solution 🔍"
keywords🏷️: ["🎓 course schedule", "📊 topological sort", "🔄 graph algorithms", "📍 kahn's algorithm", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Course Schedule II problem: find valid ordering of courses using topological sort with cycle detection. 🚀"
date: 📅 2025-11-01
---

# *01. Course Schedule II*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/course-schedule/1)

## **🧩 Problem Description**

You are given `n` courses, labeled from `0` to `n - 1` and a 2D array `prerequisites[][]` where `prerequisites[i] = [x, y]` indicates that we need to take course `y` first if we want to take course `x`.

Find the ordering of courses we should take to complete all the courses.

**Note:** There may be multiple correct orders, you just need to return any one of them. If it is impossible to finish all tasks, return an empty array. The Driver code will print `true` if you return any correct order of courses else it will print `false`.


## Code(C++)
```cpp
class Solution {
public:
    vector<int> findOrder(int n, vector<vector<int>>& prerequisites) {
        vector<vector<int>> g(n);
        vector<int> d(n);
        for(auto& p : prerequisites) g[p[1]].push_back(p[0]), d[p[0]]++;
        queue<int> q;
        vector<int> r;
        for(int i = 0; i < n; i++) if(!d[i]) q.push(i);
        while(q.size()) {
            int u = q.front(); q.pop(); r.push_back(u);
            for(int v : g[u]) if(!--d[v]) q.push(v);
        }
        return r.size() == n ? r : vector<int>{};
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<Integer> findOrder(int n, int[][] pre) {
        ArrayList<ArrayList<Integer>> g = new ArrayList<>();
        for (int i = 0; i < n; i++) g.add(new ArrayList<>());
        int[] d = new int[n];
        for (int[] p : pre) g.get(p[1]).add(p[0]); 
        for (int[] p : pre) d[p[0]]++;
        Queue<Integer> q = new LinkedList<>();
        for (int i = 0; i < n; i++) if (d[i] == 0) q.add(i);
        ArrayList<Integer> r = new ArrayList<>();
        while (!q.isEmpty()) {
            int u = q.poll(); r.add(u);
            for (int v : g.get(u)) if (--d[v] == 0) q.add(v);
        }
        return r.size() == n ? r : new ArrayList<>();
    }
}
```

## Code (Python)

```python
class Solution:
    def findOrder(self, n, prerequisites):
        g = [[] for _ in range(n)]
        d = [0] * n
        for a, b in prerequisites:
            g[b].append(a)
            d[a] += 1
        q = [i for i in range(n) if d[i] == 0]
        r = []
        while q:
            u = q.pop(0)
            r.append(u)
            for v in g[u]:
                d[v] -= 1
                if d[v] == 0: q.append(v)
        return r if len(r) == n else []
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
