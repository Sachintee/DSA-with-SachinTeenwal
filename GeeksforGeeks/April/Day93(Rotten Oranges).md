---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Graph
  - Matrix
  - Queue
---

# 🚀 _Day 93. Rotten Oranges_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/graph-gfg-160/problem/rotten-oranges2536)  

## 💡 **Problem Description:** 

Given a **matrix** `mat[][]` of size **n × m**, where each cell in the matrix can contain:
- **0** → Empty cell
- **1** → Fresh orange
- **2** → Rotten orange

A **rotten orange** at position `(i, j)` can rot adjacent fresh oranges **(up, down, left, right)** in **one unit of time**. The task is to find the **minimum time required** to rot all fresh oranges. If it's **impossible** to rot all oranges, return **-1**.


## Code(C++)
```cpp
class Solution {
public:
    int orangesRotting(vector<vector<int>>& a) {
        int n = a.size(), m = a[0].size(), t = 0, f = 0;
        queue<pair<int,int>> q;
        for(int i = 0; i < n; i++)
            for(int j = 0; j < m; j++){
                if(a[i][j] == 2) q.push({i, j});
                else if(a[i][j] == 1) f++;
            }
        if(!f) return 0;
        int d[4][2] = {{1,0}, {-1,0}, {0,1}, {0,-1}};
        while(!q.empty()){
            int sz = q.size();
            bool ch = false;
            while(sz--){
                auto p = q.front(); q.pop();
                int i = p.first, j = p.second;
                for(auto &dir : d){
                    int x = i + dir[0], y = j + dir[1];
                    if(x < 0 || y < 0 || x >= n || y >= m || a[x][y] != 1) continue;
                    a[x][y] = 2; q.push({x,y}); f--; ch = true;
                }
            }
            if(ch) t++;
        }
        return f ? -1 : t;
    }
};
```

## Code (Java)

```java
class Solution {
    public int orangesRotting(int[][] a) {
        int n = a.length, m = a[0].length, f = 0, t = 0;
        Queue<int[]> q = new LinkedList<>();
        for (int i = 0; i < n; i++)
            for (int j = 0; j < m; j++) {
                if (a[i][j] == 2)
                    q.add(new int[]{i, j});
                else if (a[i][j] == 1)
                    f++;
            }
        if (f == 0) return 0;
        int[][] d = {{1, 0}, {-1, 0}, {0, 1}, {0, -1}};
        while (!q.isEmpty()) {
            int sz = q.size();
            boolean ch = false;
            for (int k = 0; k < sz; k++) {
                int[] p = q.poll();
                int i = p[0], j = p[1];
                for (int[] dir : d) {
                    int x = i + dir[0], y = j + dir[1];
                    if (x < 0 || y < 0 || x >= n || y >= m || a[x][y] != 1)
                        continue;
                    a[x][y] = 2;
                    q.add(new int[]{x, y});
                    f--;
                    ch = true;
                }
            }
            if (ch) t++;
        }
        return f == 0 ? t : -1;
    }
}
```

## Code (Python)

```python
from collections import deque
class Solution:
    def orangesRotting(self, a):
        n, m, f, t = len(a), len(a[0]), 0, 0
        q = deque()
        for i in range(n):
            for j in range(m):
                if a[i][j] == 2:
                    q.append((i, j))
                elif a[i][j] == 1:
                    f += 1
        if not f: return 0
        d = [(1,0),(-1,0),(0,1),(0,-1)]
        while q:
            sz, ch = len(q), False
            for _ in range(sz):
                i, j = q.popleft()
                for di, dj in d:
                    x, y = i + di, j + dj
                    if x < 0 or y < 0 or x >= n or y >= m or a[x][y] != 1:
                        continue
                    a[x][y] = 2
                    q.append((x, y))
                    f -= 1
                    ch = True
            if ch: t += 1
        return t if f == 0 else -1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
