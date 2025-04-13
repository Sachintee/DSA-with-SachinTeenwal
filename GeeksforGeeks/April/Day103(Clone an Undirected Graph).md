--- ❤️ ---

# 🚀 _Day 103. Clone an Undirected Graph_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/clone-graph/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
  public:
    unordered_map<int,Node*>mp;
    unordered_set<Node*>visited;
    void cloneRemainingNodes(Node* node,Node* parent){
        if(visited.count(node)){
            return ;
        }
        visited.insert(node);
        for(auto it:node->neighbors){
           Node *newNode=mp[it->val]!=NULL ? mp[it->val] : new Node(it->val);
           mp[it->val]=newNode;
           parent->neighbors.push_back(newNode);
           cloneRemainingNodes(it,newNode);
        }
    }
    Node* cloneGraph(Node* node) {
       Node*firstNode=new Node(node->val);
       mp[node->val]=firstNode;
       visited.insert(node);
       for(auto it:node->neighbors){
           Node *newNode = mp[it->val]!=NULL ? mp[it->val] : new Node(it->val);
           mp[it->val]=newNode;
           firstNode->neighbors.push_back(newNode);
           cloneRemainingNodes(it,newNode);
       }
       return firstNode;
    }
};
```

## Code (Java)

```java
import java.util.*;

class Solution {
    private Map<Node, Node> clonedNodes = new HashMap<>();
    
    public Node cloneGraph(Node node) {
        if (node == null) {
            return null;
        }
        
        // If the node is already cloned, return the clone
        if (clonedNodes.containsKey(node)) {
            return clonedNodes.get(node);
        }
        
        // Create a clone of the node
        Node cloneNode = new Node(node.val);
        clonedNodes.put(node, cloneNode);
        
        // Recursively clone all neighbors
        for (Node neighbor : node.neighbors) {
            cloneNode.neighbors.add(cloneGraph(neighbor));
        }
        
        return cloneNode;
    }
}
```

## Code (Python)

```python
class Solution:
    def cloneGraph(self, node: 'Node') -> 'Node':
        if not node:
            return None
        
        # Dictionary to save the cloned nodes
        cloned_nodes = {}
        
        # DFS function to clone the graph
        def dfs(original_node):
            if original_node in cloned_nodes:
                return cloned_nodes[original_node]
            
            # Create a clone of the original node
            clone_node = Node(original_node.val)
            cloned_nodes[original_node] = clone_node
            
            # Recursively clone all neighbors
            for neighbor in original_node.neighbors:
                clone_node.neighbors.append(dfs(neighbor))
            
            return clone_node
        
        return dfs(node)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
