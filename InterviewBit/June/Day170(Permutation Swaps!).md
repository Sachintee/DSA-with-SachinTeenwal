--- ❤️ ---

# 🚀 _Day 170. Permutation Swaps!_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/permutation-swaps/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <unordered_map>
#include <queue>
#include <algorithm>

using namespace std;

class Solution {
public:
    int solve(vector<int>& A, vector<int>& B, vector<vector<int>>& C) {
        int n = A.size();
        unordered_map<int, vector<int>> graph;
        
        // Build the graph
        for (const auto& pair : C) {
            int x = pair[0] - 1;
            int y = pair[1] - 1;
            graph[x].push_back(y);
            graph[y].push_back(x);
        }
        
        vector<bool> visited(n, false);
        
        for (int i = 0; i < n; ++i) {
            if (!visited[i]) {
                queue<int> q;
                q.push(i);
                visited[i] = true;
                vector<int> componentIndices;
                
                while (!q.empty()) {
                    int node = q.front();
                    q.pop();
                    componentIndices.push_back(node);
                    
                    for (int neighbor : graph[node]) {
                        if (!visited[neighbor]) {
                            visited[neighbor] = true;
                            q.push(neighbor);
                        }
                    }
                }
                
                // Collect elements from A and B for the current component
                vector<int> aElements;
                vector<int> bElements;
                for (int idx : componentIndices) {
                    aElements.push_back(A[idx]);
                    bElements.push_back(B[idx]);
                }
                
                // Check if the multisets are the same
                sort(aElements.begin(), aElements.end());
                sort(bElements.begin(), bElements.end());
                if (aElements != bElements) {
                    return 0;
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
    public int solve(ArrayList<Integer> A, ArrayList<Integer> B, ArrayList<ArrayList<Integer>> C) {
        int n = A.size();
        Map<Integer, List<Integer>> graph = new HashMap<>();
        
        // Build the graph
        for (ArrayList<Integer> pair : C) {
            int x = pair.get(0) - 1;
            int y = pair.get(1) - 1;
            graph.computeIfAbsent(x, k -> new ArrayList<>()).add(y);
            graph.computeIfAbsent(y, k -> new ArrayList<>()).add(x);
        }
        
        boolean[] visited = new boolean[n];
        
        for (int i = 0; i < n; i++) {
            if (!visited[i]) {
                Queue<Integer> queue = new LinkedList<>();
                queue.add(i);
                visited[i] = true;
                List<Integer> componentIndices = new ArrayList<>();
                
                while (!queue.isEmpty()) {
                    int node = queue.poll();
                    componentIndices.add(node);
                    
                    for (int neighbor : graph.getOrDefault(node, new ArrayList<>())) {
                        if (!visited[neighbor]) {
                            visited[neighbor] = true;
                            queue.add(neighbor);
                        }
                    }
                }
                
                // Collect elements from A and B for the current component
                List<Integer> aElements = new ArrayList<>();
                List<Integer> bElements = new ArrayList<>();
                for (int idx : componentIndices) {
                    aElements.add(A.get(idx));
                    bElements.add(B.get(idx));
                }
                
                // Check if the multisets are the same
                Collections.sort(aElements);
                Collections.sort(bElements);
                if (!aElements.equals(bElements)) {
                    return 0;
                }
            }
        }
        return 1;
    }
}
```

## Code (Python)

```python
from collections import defaultdict, deque

class Solution:
    def solve(self, A, B, C):
        n = len(A)
        # Create an adjacency list for the graph
        graph = defaultdict(list)
        for x, y in C:
            graph[x-1].append(y-1)
            graph[y-1].append(x-1)
        
        visited = [False] * n
        # For each connected component, collect indices and check if the corresponding A and B elements match
        for i in range(n):
            if not visited[i]:
                queue = deque()
                queue.append(i)
                visited[i] = True
                component_indices = []
                while queue:
                    node = queue.popleft()
                    component_indices.append(node)
                    for neighbor in graph[node]:
                        if not visited[neighbor]:
                            visited[neighbor] = True
                            queue.append(neighbor)
                # Collect elements from A and B for the current component
                a_elements = [A[idx] for idx in component_indices]
                b_elements = [B[idx] for idx in component_indices]
                # Check if the multisets are the same
                if sorted(a_elements) != sorted(b_elements):
                    return 0
        return 1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
