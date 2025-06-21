--- ❤️ ---

# 🚀 _Day 172. Two teams?_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/two-teams/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <queue>
using namespace std;

class Solution {
public:
    int solve(int A, vector<vector<int>>& B) {
        // Build the adjacency list
        vector<vector<int>> adj(A + 1);
        for (const auto& edge : B) {
            int u = edge[0];
            int v = edge[1];
            adj[u].push_back(v);
            adj[v].push_back(u);
        }
        
        vector<int> color(A + 1, -1);
        
        for (int i = 1; i <= A; ++i) {
            if (color[i] == -1) {
                queue<int> q;
                q.push(i);
                color[i] = 0;
                
                while (!q.empty()) {
                    int node = q.front();
                    q.pop();
                    
                    for (int neighbor : adj[node]) {
                        if (color[neighbor] == -1) {
                            color[neighbor] = color[node] ^ 1;
                            q.push(neighbor);
                        } else if (color[neighbor] == color[node]) {
                            return 0;
                        }
                    }
                }
            }
        }
        return 1;
    }
};
```

## Code (Java)

```java
import java.util.*;

class Solution {
    public int solve(int A, int[][] B) {
        // Build the adjacency list
        List<List<Integer>> adj = new ArrayList<>();
        for (int i = 0; i <= A; i++) {
            adj.add(new ArrayList<>());
        }
        for (int[] edge : B) {
            int u = edge[0];
            int v = edge[1];
            adj.get(u).add(v);
            adj.get(v).add(u);
        }
        
        int[] color = new int[A + 1];
        Arrays.fill(color, -1);
        
        for (int i = 1; i <= A; i++) {
            if (color[i] == -1) {
                Queue<Integer> queue = new LinkedList<>();
                queue.add(i);
                color[i] = 0;
                
                while (!queue.isEmpty()) {
                    int node = queue.poll();
                    
                    for (int neighbor : adj.get(node)) {
                        if (color[neighbor] == -1) {
                            color[neighbor] = color[node] ^ 1;
                            queue.add(neighbor);
                        } else if (color[neighbor] == color[node]) {
                            return 0;
                        }
                    }
                }
            }
        }
        return 1;
    }
}
```

## Code (Python)

```python
from collections import deque

class Solution:
    def solve(self, A, B):
        # Build the adjacency list
        adj = [[] for _ in range(A + 1)]
        for u, v in B:
            adj[u].append(v)
            adj[v].append(u)
        
        color = [-1] * (A + 1)
        
        for i in range(1, A + 1):
            if color[i] == -1:
                queue = deque()
                queue.append(i)
                color[i] = 0
                
                while queue:
                    node = queue.popleft()
                    for neighbor in adj[node]:
                        if color[neighbor] == -1:
                            color[neighbor] = color[node] ^ 1
                            queue.append(neighbor)
                        elif color[neighbor] == color[node]:
                            return 0
        return 1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
