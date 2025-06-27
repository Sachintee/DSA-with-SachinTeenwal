--- ❤️ ---

# 🚀 _Day 178. Path with good nodes!_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/path-with-good-nodes/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <stack>
#include <utility>
using namespace std;

class Solution {
public:
    int solve(vector<int>& A, vector<vector<int>>& B, int C) {
        int N = A.size();
        vector<vector<int>> tree(N + 1);
        for (auto& edge : B) {
            int u = edge[0];
            int v = edge[1];
            tree[u].push_back(v);
            tree[v].push_back(u);
        }
        
        int count = 0;
        stack<pair<int, pair<int, int>>> stk; // {node, {parent, good_count}}
        stk.push({1, {-1, 0}});
        
        while (!stk.empty()) {
            auto current = stk.top();
            stk.pop();
            int node = current.first;
            int parent = current.second.first;
            int good_count = current.second.second;
            
            int current_good = good_count + A[node - 1];
            if (current_good > C) {
                continue;
            }
            
            bool is_leaf = true;
            for (int neighbor : tree[node]) {
                if (neighbor != parent) {
                    is_leaf = false;
                    stk.push({neighbor, {node, current_good}});
                }
            }
            
            if (is_leaf && current_good <= C) {
                count++;
            }
        }
        
        return count;
    }
};
```

## Code (Java)

```java
import java.util.*;

class Solution {
    public int solve(int[] A, int[][] B, int C) {
        int N = A.length;
        List<List<Integer>> tree = new ArrayList<>();
        for (int i = 0; i <= N; i++) {
            tree.add(new ArrayList<>());
        }
        for (int[] edge : B) {
            int u = edge[0];
            int v = edge[1];
            tree.get(u).add(v);
            tree.get(v).add(u);
        }
        
        int count = 0;
        Stack<int[]> stack = new Stack<>(); // {node, parent, good_count}
        stack.push(new int[]{1, -1, 0});
        
        while (!stack.isEmpty()) {
            int[] current = stack.pop();
            int node = current[0];
            int parent = current[1];
            int good_count = current[2];
            
            int current_good = good_count + A[node - 1];
            if (current_good > C) {
                continue;
            }
            
            boolean is_leaf = true;
            for (int neighbor : tree.g
```

## Code (Python)

```python
import sys
from collections import deque

sys.setrecursionlimit(1 << 25)

class Solution:
    def solve(self, A, B, C):
        # Build the tree as an adjacency list
        tree = [[] for _ in range(len(A) + 1)]
        for u, v in B:
            tree[u].append(v)
            tree[v].append(u)
        
        count = 0
        
        # We'll use DFS to traverse the tree
        stack = [(1, None, 0)]  # (node, parent, good_count)
        
        while stack:
            node, parent, good_count = stack.pop()
            current_good = good_count + A[node - 1]  # A is 0-based for nodes 1..N
            
            if current_good > C:
                continue  # No need to proceed further on this path
            
            is_leaf = True
            for neighbor in tree[node]:
                if neighbor != parent:
                    is_leaf = False
                    stack.append((neighbor, node, current_good))
            
            if is_leaf and current_good <= C:
                count += 1
        
        return count
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
