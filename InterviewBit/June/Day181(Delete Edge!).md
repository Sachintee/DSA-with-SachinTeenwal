--- ❤️ ---

# 🚀 _Day 181. Delete Edge!_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/delete-edge/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <stack>
#include <algorithm>
using namespace std;

const int MOD = 1e9 + 7;

class Solution {
public:
    int deleteEdge(vector<int>& A, vector<vector<int>>& B) {
        int n = A.size();
        vector<vector<int>> adj(n + 1);
        for (auto& edge : B) {
            int u = edge[0];
            int v = edge[1];
            adj[u].push_back(v);
            adj[v].push_back(u);
        }

        long long total_sum = 0;
        for (int weight : A) {
            total_sum += weight;
        }

        long long max_product = 0;
        vector<long long> subtree_sum(n + 1, 0);
        vector<int> parent(n + 1, 0);
        stack<pair<int, bool>> stk;
        stk.push({1, false});

        while (!stk.empty()) {
            auto [node, processed] = stk.top();
            stk.pop();
            if (!processed) {
                stk.push({node, true});
                for (int neighbor : adj[node]) {
                    if (neighbor != parent[node]) {
                        parent[neighbor] = node;
                        stk.push({neighbor, false});
                    }
                }
            } else {
                subtree_sum[node] = A[node - 1];
                for (int neighbor : adj[node]) {
                    if (neighbor != parent[node]) {
                        subtree_sum[node] += subtree_sum[neighbor];
                    }
                }
                long long current_product = subtree_sum[node] * (total_sum - subtree_sum[node]);
                if (current_product > max_product) {
                    max_product = current_product;
                }
            }
        }

        return max_product % MOD;
    }
};
```

## Code (Java)

```java
import java.util.*;

class Solution {
    private static final int MOD = 1_000_000_007;

    public int deleteEdge(int[] A, int[][] B) {
        int n = A.length;
        List<List<Integer>> adj = new ArrayList<>();
        for (int i = 0; i <= n; i++) {
            adj.add(new ArrayList<>());
        }
        for (int[] edge : B) {
            int u = edge[0];
            int v = edge[1];
            adj.get(u).add(v);
            adj.get(v).add(u);
        }

        long totalSum = 0;
        for (int weight : A) {
            totalSum += weight;
        }

        long maxProduct = 0;
        long[] subtreeSum = new long[n + 1];
        int[] parent = new int[n + 1];
        Deque<Pair<Integer, Boolean>> stack = new ArrayDeque<>();
        stack.push(new Pair<>(1, false));

        while (!stack.isEmpty()) {
            Pair<Integer, Boolean> pair = stack.pop();
            int node = pair.getKey();
            boolean processed = pair.getValue();
            if (!processed) {
                stack.push(new Pair<>(node, true));
                for (int neighbor : adj.get(node)) {
                    if (neighbor != parent[node]) {
                        parent[neighbor] = node;
                        stack.push(new Pair<>(neighbor, false));
                    }
                }
            } else {
                subtreeSum[node] = A[node - 1];
                for (int neighbor : adj.get(node)) {
                    if (neighbor != parent[node]) {
                        subtreeSum[node] += subtreeSum[neighbor];
                    }
                }
                long currentProduct = subtreeSum[node] * (totalSum - subtreeSum[node]);
                if (currentProduct > maxProduct) {
                    maxProduct = currentProduct;
                }
            }
        }

        return (int) (maxProduct % MOD);
    }

    static class Pair<K, V> {
        private K key;
        private V value;

        public Pair(K key, V value) {
            this.key = key;
            this.value = value;
        }

        public K getKey() {
            return key;
        }

        public V getValue() {
            return value;
        }
    }
}
```

## Code (Python)

```python
import sys
from collections import deque

MOD = 10**9 + 7

class Solution:
    def deleteEdge(self, A, B):
        n = len(A)
        adj = [[] for _ in range(n + 1)]
        for u, v in B:
            adj[u].append(v)
            adj[v].append(u)
        
        total_sum = sum(A)
        max_product = 0
        
        # To avoid recursion depth issues, use iterative DFS
        parent = [0] * (n + 1)
        subtree_sum = [0] * (n + 1)
        stack = [(1, None, False)]
        
        while stack:
            node, par, processed = stack.pop()
            if not processed:
                stack.append((node, par, True))
                for neighbor in adj[node]:
                    if neighbor != par:
                        stack.append((neighbor, node, False))
            else:
                subtree_sum[node] = A[node - 1]
                for neighbor in adj[node]:
                    if neighbor != par:
                        subtree_sum[node] += subtree_sum[neighbor]
                # For each child, calculate the product
                current_product = subtree_sum[node] * (total_sum - subtree_sum[node])
                if current_product > max_product:
                    max_product = current_product
        
        return max_product % MOD
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
