--- ❤️ ---

# 🚀 _Day 173. Commutable Islands_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/commutable-islands/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <algorithm>
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
                parent[u] = parent[parent[u]];
                u = parent[u];
            }
            return u;
        };
        
        auto union_ = [&](int u, int v) {
            int u_root = find(u);
            int v_root = find(v);
            if (u_root == v_root) {
                return false;
            }
            parent[v_root] = u_root;
            return true;
        };
        
        sort(B.begin(), B.end(), [](const vector<int>& a, const vector<int>& b) {
            return a[2] < b[2];
        });
        
        int total_cost = 0;
        int edges_used = 0;
        
        for (const auto& bridge : B) {
            int u = bridge[0];
            int v = bridge[1];
            int cost = bridge[2];
            if (union_(u, v)) {
                total_cost += cost;
                edges_used++;
                if (edges_used == A - 1) {
                    break;
                }
            }
        }
        
        return total_cost;
    }
};
```

## Code (Java)

```java
import java.util.*;

class Solution {
    public int solve(int A, int[][] B) {
        int[] parent = new int[A + 1];
        for (int i = 1; i <= A; i++) {
            parent[i] = i;
        }
        
        class UnionFind {
            int find(int u) {
                while (parent[u] != u) {
                    parent[u] = parent[parent[u]];
                    u = parent[u];
                }
                return u;
            }
            
            boolean union(int u, int v) {
                int uRoot = find(u);
                int vRoot = find(v);
                if (uRoot == vRoot) {
                    return false;
                }
                parent[vRoot] = uRoot;
                return true;
            }
        }
        
        UnionFind uf = new UnionFind();
        
        Arrays.sort(B, (a, b) -> Integer.compare(a[2], b[2]));
        
        int totalCost = 0;
        int edgesUsed = 0;
        
        for (int[] bridge : B) {
            int u = bridge[0];
            int v = bridge[1];
            int cost = bridge[2];
            if (uf.union(u, v)) {
                totalCost += cost;
                edgesUsed++;
                if (edgesUsed == A - 1) {
                    break;
                }
            }
        }
        
        return totalCost;
    }
}
```

## Code (Python)

```python
class Solution:
    def solve(self, A, B):
        parent = [i for i in range(A + 1)]
        
        def find(u):
            while parent[u] != u:
                parent[u] = parent[parent[u]]
                u = parent[u]
            return u
        
        def union(u, v):
            u_root = find(u)
            v_root = find(v)
            if u_root == v_root:
                return False
            parent[v_root] = u_root
            return True
        
        B.sort(key=lambda x: x[2])
        total_cost = 0
        edges_used = 0
        
        for u, v, cost in B:
            if union(u, v):
                total_cost += cost
                edges_used += 1
                if edges_used == A - 1:
                    break
        
        return total_cost
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
