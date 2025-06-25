--- ❤️ ---

# 🚀 _Day 176. Cycle in Undirected Graph_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/cycle-in-undirected-graph/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
using namespace std;

class Solution {
public:
    int solve(int A, vector<vector<int>>& B) {
        vector<int> parent(A + 1);
        for (int i = 1; i <= A; ++i) {
            parent[i] = i;
        }
        
        auto find = [&](int u) {
            while (parent[u] != u) {
                parent[u] = parent[parent[u]]; // Path compression
                u = parent[u];
            }
            return u;
        };
        
        for (const auto& edge : B) {
            int u = edge[0];
            int v = edge[1];
            int root_u = find(u);
            int root_v = find(v);
            if (root_u == root_v) {
                return 1;
            }
            parent[root_u] = root_v;
        }
        return 0;
    }
};
```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public int solve(int A, int[][] B) {
        int[] parent = new int[A + 1];
        for (int i = 1; i <= A; i++) {
            parent[i] = i;
        }
        
        for (int[] edge : B) {
            int u = edge[0];
            int v = edge[1];
            int rootU = find(u, parent);
            int rootV = find(v, parent);
            if (rootU == rootV) {
                return 1;
            }
            parent[rootU] = rootV;
        }
        return 0;
    }
    
    private int find(int u, int[] parent) {
        while (parent[u] != u) {
            parent[u] = parent[parent[u]]; // Path compression
            u = parent[u];
        }
        return u;
    }
}
```

## Code (Python)

```python
class Solution:
    def solve(self, A, B):
        parent = [i for i in range(A + 1)]  # 1-based indexing
        
        def find(u):
            while parent[u] != u:
                parent[u] = parent[parent[u]]  # Path compression
                u = parent[u]
            return u
        
        for u, v in B:
            root_u = find(u)
            root_v = find(v)
            if root_u == root_v:
                return 1
            parent[root_u] = root_v
        return 0
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
