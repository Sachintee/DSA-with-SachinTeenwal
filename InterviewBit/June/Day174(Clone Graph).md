--- ❤️ ---

# 🚀 _Day 174. Clone Graph_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/clone-graph/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <unordered_map>
#include <queue>
using namespace std;

// Definition for undirected graph.
struct UndirectedGraphNode {
    int label;
    vector<UndirectedGraphNode *> neighbors;
    UndirectedGraphNode(int x) : label(x) {};
};

class Solution {
public:
    UndirectedGraphNode *cloneGraph(UndirectedGraphNode *node) {
        if (!node) return nullptr;
        
        unordered_map<UndirectedGraphNode*, UndirectedGraphNode*> clonedNodes;
        queue<UndirectedGraphNode*> q;
        
        // Clone the root node
        UndirectedGraphNode* clonedNode = new UndirectedGraphNode(node->label);
        clonedNodes[node] = clonedNode;
        q.push(node);
        
        while (!q.empty()) {
            UndirectedGraphNode* current = q.front();
            q.pop();
            
            for (UndirectedGraphNode* neighbor : current->neighbors) {
                if (clonedNodes.find(neighbor) == clonedNodes.end()) {
                    // Clone the neighbor if not already cloned
                    UndirectedGraphNode* clonedNeighbor = new UndirectedGraphNode(neighbor->label);
                    clonedNodes[neighbor] = clonedNeighbor;
                    q.push(neighbor);
                }
                // Add the cloned neighbor to the current cloned node's neighbors
                clonedNodes[current]->neighbors.push_back(clonedNodes[neighbor]);
            }
        }
        
        return clonedNodes[node];
    }
};
```

## Code (Java)

```java
import java.util.*;

class UndirectedGraphNode {
    int label;
    List<UndirectedGraphNode> neighbors;
    UndirectedGraphNode(int x) { 
        label = x; 
        neighbors = new ArrayList<UndirectedGraphNode>(); 
    }
}

public class Solution {
    public UndirectedGraphNode cloneGraph(UndirectedGraphNode node) {
        if (node == null) return null;
        
        Map<UndirectedGraphNode, UndirectedGraphNode> clonedNodes = new HashMap<>();
        Queue<UndirectedGraphNode> queue = new LinkedList<>();
        
        // Clone the root node
        UndirectedGraphNode clonedNode = new UndirectedGraphNode(node.label);
        clonedNodes.put(node, clonedNode);
        queue.add(node);
        
        while (!queue.isEmpty()) {
            UndirectedGraphNode current = queue.poll();
            
            for (UndirectedGraphNode neighbor : current.neighbors) {
                if (!clonedNodes.containsKey(neighbor)) {
                    // Clone the neighbor if not already cloned
                    UndirectedGraphNode clonedNeighbor = new UndirectedGraphNode(neighbor.label);
                    clonedNodes.put(neighbor, clonedNeighbor);
                    queue.add(neighbor);
                }
                // Add the cloned neighbor to the current cloned node's neighbors
                clonedNodes.get(current).neighbors.add(clonedNodes.get(neighbor));
            }
        }
        
        return clonedNodes.get(node);
    }
}
```

## Code (Python)

```python
from collections import deque

class UndirectedGraphNode:
    def __init__(self, x):
        self.label = x
        self.neighbors = []

class Solution:
    def cloneGraph(self, node):
        if not node:
            return None
        
        # Dictionary to save the cloned nodes
        cloned_nodes = {}
        
        # Queue for BFS
        queue = deque()
        queue.append(node)
        
        # Clone the root node
        cloned_node = UndirectedGraphNode(node.label)
        cloned_nodes[node] = cloned_node
        
        while queue:
            current_node = queue.popleft()
            for neighbor in current_node.neighbors:
                if neighbor not in cloned_nodes:
                    # Clone the neighbor if not already cloned
                    cloned_neighbor = UndirectedGraphNode(neighbor.label)
                    cloned_nodes[neighbor] = cloned_neighbor
                    queue.append(neighbor)
                # Add the cloned neighbor to the current cloned node's neighbors
                cloned_nodes[current_node].neighbors.append(cloned_nodes[neighbor])
        
        return cloned_nodes[node]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
