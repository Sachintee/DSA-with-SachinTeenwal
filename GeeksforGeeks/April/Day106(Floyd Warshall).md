---
Difficulty: Medium
Source: 160 Days of Problem Solving
Tags:
  - Graph
  - Dynamic Programming
---

# 🚀 _Day 106. Floyd Warshall_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/graph-gfg-160/problem/implementing-floyd-warshall2042)  



## 💡 **Problem Description:**

You are given a weighted directed graph represented by an adjacency matrix `dist[][]` of size `n x n`, where `dist[i][j]` represents the weight of the edge from node `i` to node `j`. If there is no direct edge, `dist[i][j]` is set to a large value (e.g., `10^8`) representing infinity.  
The graph may contain negative edge weights, but it does not contain any negative weight cycles.

Your task is to compute the shortest distance between every pair of nodes `(i, j)` by modifying the distances in-place.


## Code(C++)
```cpp
class Solution {
  public:
    void floydWarshall(vector<vector<int>> &d) {
        int n = d.size(), inf = 1e8;
        for (int k = 0; k < n; ++k)
            for (int i = 0; i < n; ++i)
                for (int j = 0; j < n; ++j)
                    if (d[i][k] < inf && d[k][j] < inf && d[i][j] > d[i][k] + d[k][j])
                        d[i][j] = d[i][k] + d[k][j];
    }
};
```

## Code (Java)

```java
class Solution {
    public void floydWarshall(int[][] d) {
        int n = d.length, inf = 100000000;
        for (int k = 0; k < n; k++)
            for (int i = 0; i < n; i++)
                for (int j = 0; j < n; j++)
                    if (d[i][k] < inf && d[k][j] < inf && d[i][j] > d[i][k] + d[k][j])
                        d[i][j] = d[i][k] + d[k][j];
    }
}
```

## Code (Python)

```python
class Solution:
    def floydWarshall(self, d):
        n, inf = len(d), 100000000
        for k in range(n):
            for i in range(n):
                for j in range(n):
                    if d[i][k] < inf and d[k][j] < inf and d[i][j] > d[i][k] + d[k][j]:
                        d[i][j] = d[i][k] + d[k][j]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
