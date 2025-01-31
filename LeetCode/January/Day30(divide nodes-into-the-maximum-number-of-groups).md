--- ❤️ ---

# 🚀 _Day 30. divide nodes-into-the-maximum-number-of-groups_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/divide-nodes-into-the-maximum-number-of-groups/?envType=daily-question&envId=2025-01-30)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int magnificentSets(int n, vector<vector<int>>& edges) {
        vector<int> g[n];
        for (auto& e : edges) {
            int a = e[0] - 1, b = e[1] - 1;
            g[a].push_back(b);
            g[b].push_back(a);
        }
        vector<int> d(n);
        for (int i = 0; i < n; ++i) {
            queue<int> q{{i}};
            vector<int> dist(n);
            dist[i] = 1;
            int mx = 1;
            int root = i;
            while (q.size()) {
                int a = q.front();
                q.pop();
                root = min(root, a);
                for (int b : g[a]) {
                    if (dist[b] == 0) {
                        dist[b] = dist[a] + 1;
                        mx = max(mx, dist[b]);
                        q.push(b);
                    } else if (abs(dist[b] - dist[a]) != 1) {
                        return -1;
                    }
                }
            }
            d[root] = max(d[root], mx);
        }
        return accumulate(d.begin(), d.end(), 0);
    }
};
```

## Code (Java)

```java
class Solution {
    public int magnificentSets(int n, int[][] edges) {
        List<Integer>[] g = new List[n];
        Arrays.setAll(g, k -> new ArrayList<>());
        for (var e : edges) {
            int a = e[0] - 1, b = e[1] - 1;
            g[a].add(b);
            g[b].add(a);
        }
        int[] d = new int[n];
        int[] dist = new int[n];
        for (int i = 0; i < n; ++i) {
            Deque<Integer> q = new ArrayDeque<>();
            q.offer(i);
            Arrays.fill(dist, 0);
            dist[i] = 1;
            int mx = 1;
            int root = i;
            while (!q.isEmpty()) {
                int a = q.poll();
                root = Math.min(root, a);
                for (int b : g[a]) {
                    if (dist[b] == 0) {
                        dist[b] = dist[a] + 1;
                        mx = Math.max(mx, dist[b]);
                        q.offer(b);
                    } else if (Math.abs(dist[b] - dist[a]) != 1) {
                        return -1;
                    }
                }
            }
            d[root] = Math.max(d[root], mx);
        }
        return Arrays.stream(d).sum();
    }
}
```

## Code (Python)

```python
class Solution:
    def magnificentSets(self, n: int, edges: List[List[int]]) -> int:
        g = [[] for _ in range(n)]
        for a, b in edges:
            g[a - 1].append(b - 1)
            g[b - 1].append(a - 1)
        d = defaultdict(int)
        for i in range(n):
            q = deque([i])
            dist = [0] * n
            dist[i] = mx = 1
            root = i
            while q:
                a = q.popleft()
                root = min(root, a)
                for b in g[a]:
                    if dist[b] == 0:
                        dist[b] = dist[a] + 1
                        mx = max(mx, dist[b])
                        q.append(b)
                    elif abs(dist[b] - dist[a]) != 1:
                        return -1
            d[root] = max(d[root], mx)
        return sum(d.values())
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
 <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>635</h4>
