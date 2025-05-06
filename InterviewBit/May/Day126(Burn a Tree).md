--- ❤️ ---

# 🚀 _Day 126. Burn a Tree_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/burn-a-tree/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <unordered_map>
#include <queue>
#include <unordered_set>
using namespace std;

// Definition for a binary tree node.
struct TreeNode {
    int val;
    TreeNode *left;
    TreeNode *right;
    TreeNode(int x) : val(x), left(NULL), right(NULL) {}
};

class Solution {
public:
    int solve(TreeNode* A, int B) {
        if (!A) return 0;

        unordered_map<TreeNode*, TreeNode*> parent_map;
        TreeNode* target_node = nullptr;
        queue<TreeNode*> q;
        q.push(A);
        parent_map[A] = nullptr;

        // Step 1: Create parent map and find the target node
        while (!q.empty()) {
            TreeNode* current = q.front();
            q.pop();
            if (current->val == B) {
                target_node = current;
            }
            if (current->left) {
                parent_map[current->left] = current;
                q.push(current->left);
            }
            if (current->right) {
                parent_map[current->right] = current;
                q.push(current->right);
            }
        }

        if (!target_node) return 0;

        // Step 2: BFS to simulate burning
        unordered_set<TreeNode*> burned;
        queue<TreeNode*> burn_queue;
        burn_queue.push(target_node);
        burned.insert(target_node);
        int time = 0;

        while (!burn_queue.empty()) {
            int level_size = burn_queue.size();
            bool burned_this_level = false;
            for (int i = 0; i < level_size; ++i) {
                TreeNode* current = burn_queue.front();
                burn_queue.pop();
                // Check left child
                if (current->left && burned.find(current->left) == burned.end()) {
                    burned.insert(current->left);
                    burn_queue.push(current->left);
                    burned_this_level = true;
                }
                // Check right child
                if (current->right && burned.find(current->right) == burned.end()) {
                    burned.insert(current->right);
                    burn_queue.push(current->right);
                    burned_this_level = true;
                }
                // Check parent
                TreeNode* parent = parent_map[current];
                if (parent && burned.find(parent) == burned.end()) {
                    burned.insert(parent);
                    burn_queue.push(parent);
                    burned_this_level = true;
                }
            }
            if (burned_this_level) {
                time++;
            }
        }
        return time;
    }
};
```

## Code (Java)

```java
import java.util.*;

// Definition for a binary tree node.
class TreeNode {
    int val;
    TreeNode left;
    TreeNode right;
    TreeNode(int x) { val = x; }
}

public class Solution {
    public int solve(TreeNode A, int B) {
        if (A == null) return 0;

        Map<TreeNode, TreeNode> parentMap = new HashMap<>();
        TreeNode targetNode = null;
        Queue<TreeNode> queue = new LinkedList<>();
        queue.add(A);
        parentMap.put(A, null);

        // Step 1: Create parent map and find the target node
        while (!queue.isEmpty()) {
            TreeNode current = queue.poll();
            if (current.val == B) {
                targetNode = current;
            }
            if (current.left != null) {
                parentMap.put(current.left, current);
                queue.add(current.left);
            }
            if (current.right != null) {
                parentMap.put(current.right, current);
                queue.add(current.right);
            }
        }

        if (targetNode == null) return 0;

        // Step 2: BFS to simulate burning
        Set<TreeNode> burned = new HashSet<>();
        Queue<TreeNode> burnQueue = new LinkedList<>();
        burnQueue.add(targetNode);
        burned.add(targetNode);
        int time = 0;

        while (!burnQueue.isEmpty()) {
            int levelSize = burnQueue.size();
            boolean burnedThisLevel = false;
            for (int i = 0; i < levelSize; i++) {
                TreeNode current = burnQueue.poll();
                // Check left child
                if (current.left != null && !burned.contains(current.left)) {
                    burned.add(current.left);
                    burnQueue.add(current.left);
                    burnedThisLevel = true;
                }
                // Check right child
                if (current.right != null && !burned.contains(current.right)) {
                    burned.add(current.right);
                    burnQueue.add(current.right);
                    burnedThisLevel = true;
                }
                // Check parent
                TreeNode parent = parentMap.get(current);
                if (parent != null && !burned.contains(parent)) {
                    burned.add(parent);
                    burnQueue.add(parent);
                    burnedThisLevel = true;
                }
            }
            if (burnedThisLevel) {
                time++;
            }
        }
        return time;
    }
}
```

## Code (Python)

```python
from collections import deque

# Definition for a binary tree node.
class TreeNode:
    def __init__(self, x):
        self.val = x
        self.left = None
        self.right = None

class Solution:
    def solve(self, A, B):
        if not A:
            return 0
        
        # Step 1: Create a parent map and find the target node
        parent_map = {}
        target_node = None
        stack = [(A, None)]  # (node, parent)
        
        while stack:
            node, parent = stack.pop()
            parent_map[node] = parent
            if node.val == B:
                target_node = node
            if node.right:
                stack.append((node.right, node))
            if node.left:
                stack.append((node.left, node))
        
        if not target_node:
            return 0
        
        # Step 2: BFS to simulate burning
        burned = set()
        queue = deque()
        queue.append(target_node)
        burned.add(target_node)
        time = 0
        
        while queue:
            level_size = len(queue)
            burned_this_level = False
            for _ in range(level_size):
                current = queue.popleft()
                # Check left child
                if current.left and current.left not in burned:
                    burned.add(current.left)
                    queue.append(current.left)
                    burned_this_level = True
                # Check right child
                if current.right and current.right not in burned:
                    burned.add(current.right)
                    queue.append(current.right)
                    burned_this_level = True
                # Check parent
                parent = parent_map.get(current)
                if parent and parent not in burned:
                    burned.add(parent)
                    queue.append(parent)
                    burned_this_level = True
            if burned_this_level:
                time += 1
        
        return time
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
