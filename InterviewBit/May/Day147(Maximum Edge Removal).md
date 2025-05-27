--- ❤️ ---

# 🚀 _Day 147. Maximum Edge Removal_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/maximum-edge-removal/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <unordered_map>
#include <stack>
#include <utility>

using namespace std;

class Solution {
public:
    int solve(int A, vector<vector<int>>& B) {
        unordered_map<int, vector<int>> tree;
        for (const auto& edge : B) {
            int u = edge[0];
            int v = edge[1];
            tree[u].push_back(v);
            tree[v].push_back(u);
        }

        vector<bool> visited(A + 1, false);
        vector<int> size(A + 1, 0);
        int res = 0;

        stack<pair<int, int>> stk; // node, parent
        stack<pair<int, int>> process;
        stk.push({1, -1});

        while (!stk.empty()) {
            auto [node, parent] = stk.top();
            stk.pop();
            process.push({node, parent});

            for (int neighbor : tree[node]) {
                if (neighbor != parent) {
                    stk.push({neighbor, node});
                }
            }
        }

        while (!process.empty()) {
            auto [node, parent] = process.top();
            process.pop();
            size[node] = 1; // count the node itself

            for (int neighbor : tree[node]) {
                if (neighbor != parent) {
                    size[node] += size[neighbor];
                }
            }

            if (size[node] % 2 == 0 && parent != -1) {
                res++;
            }
        }

        return res;
    }
};
```

## Code (Java)

```java
import java.util.*;

class Solution {
    public int solve(int A, int[][] B) {
        Map<Integer, List<Integer>> tree = new HashMap<>();
        for (int[] edge : B) {
            int u = edge[0];
            int v = edge[1];
            tree.computeIfAbsent(u, k -> new ArrayList<>()).add(v);
            tree.computeIfAbsent(v, k -> new ArrayList<>()).add(u);
        }

        boolean[] visited = new boolean[A + 1];
        int[] size = new int[A + 1];
        int res = 0;

        Stack<int[]> stack = new Stack<>();
        Stack<int[]> process = new Stack<>();
        stack.push(new int[]{1, -1});

        while (!stack.isEmpty()) {
            int[] current = stack.pop();
            int node = current[0];
            int parent = current[1];
            process.push(new int[]{node, parent});

            List<Integer> neighbors = tree.getOrDefault(node, new ArrayList<>());
            for (int neighbor : neighbors) {
                if (neighbor != parent) {
                    stack.push(new int[]{neighbor, node});
                }
            }
        }

        while (!process.isEmpty()) {
            int[] current = process.pop();
            int node = current[0];
            int parent = current[1];
            size[node] = 1; // count the node itself

            List<Integer> neighbors = tree.getOrDefault(node, new ArrayList<>());
            for (int neighbor : neighbors) {
                if (neighbor != parent) {
                    size[node] += size[neighbor];
                }
            }

            if (size[node] % 2 == 0 && parent != -1) {
                res++;
            }
        }

        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def solve(self, A, B):
        from collections import defaultdict

        # Build the adjacency list for the tree
        tree = defaultdict(list)
        for u, v in B:
            tree[u].append(v)
            tree[v].append(u)
        
        # To keep track of visited nodes
        visited = [False] * (A + 1)
        # To store the size of each subtree
        size = [0] * (A + 1)
        # To count the number of edges that can be removed
        res = 0

        # Perform DFS
        stack = [(1, None, False)]
        
        while stack:
            node, parent, processed = stack.pop()
            if not processed:
                stack.append((node, parent, True))
                # Push children onto the stack
                for neighbor in tree[node]:
                    if neighbor != parent:
                        stack.append((neighbor, node, False))
            else:
                size[node] = 1  # count the node itself
                for neighbor in tree[node]:
                    if neighbor != parent:
                        size[node] += size[neighbor]
                # If the subtree size is even, we can remove the edge to parent (if exists)
                if size[node] % 2 == 0 and parent is not None:
                    res += 1
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
