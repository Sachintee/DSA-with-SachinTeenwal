---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Graph
  - DFS
---

# 🚀 _Day 95. Find the Number of Islands_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/graph-gfg-160/problem/find-the-number-of-islands)

## 💡 **Problem Description:** 

Given a grid of size **n × m** consisting of `'W'` (Water) and `'L'` (Land), find the number of islands. An island is formed by connecting adjacent lands in any of the 8 directions (horizontally, vertically, or diagonally) and is surrounded by water or the grid boundary.


## Code(C++)
```cpp
class Solution{
public:
    int countIslands(vector<vector<char>>& g){
        int n = g.size(), m = g[0].size(), ans = 0;
        function<void(int,int)> f = [&](int i, int j){
            if(i < 0 || i >= n || j < 0 || j >= m || g[i][j] == 'W') return;
            g[i][j] = 'W';
            for(int a = -1; a <= 1; a++) 
                for(int b = -1; b <= 1; b++) 
                    f(i + a, j + b);
        };
        for(int i = 0; i < n; i++)
            for(int j = 0; j < m; j++)
                if(g[i][j] == 'L') { ans++; f(i, j); }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution{
    public int countIslands(char[][] g){
        int n = g.length, m = g[0].length, ans = 0;
        for(int i = 0; i < n; i++)
            for(int j = 0; j < m; j++)
                if(g[i][j]=='L'){ ans++; dfs(g, i, j, n, m); }
        return ans;
    }
    void dfs(char[][] g, int i, int j, int n, int m){
        if(i < 0 || j < 0 || i >= n || j >= m || g[i][j]=='W') return;
        g[i][j] = 'W';
        for(int a = -1; a <= 1; a++)
            for(int b = -1; b <= 1; b++)
                dfs(g, i + a, j + b, n, m);
    }
}
```

## Code (Python)

```python
class Solution:
    def numIslands(self, g):
        n, m, ans = len(g), len(g[0]), 0
        def dfs(i, j):
            if i < 0 or j < 0 or i >= n or j >= m or g[i][j]=='W': return
            g[i][j] = 'W'
            for a in (-1,0,1):
                for b in (-1,0,1):
                    dfs(i+a, j+b)
        for i in range(n):
            for j in range(m):
                if g[i][j]=='L':
                    ans += 1
                    dfs(i, j)
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
