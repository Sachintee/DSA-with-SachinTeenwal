--- ❤️ ---

# 🚀 _Day 127. Cousins in Binary Tree_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/cousins-in-binary-tree/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <queue>
#include <utility>
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
    vector<int> solve(TreeNode* A, int B) {
        vector<int> cousins;
        if (!A) return cousins;
        
        queue<pair<TreeNode*, TreeNode*>> q; // (node, parent)
        q.push({A, nullptr});
        bool found = false;
        TreeNode* target_parent = nullptr;
        
        while (!q.empty()) {
            int level_size = q.size();
            vector<pair<int, TreeNode*>> current_level;
            
            for (int i = 0; i < level_size; ++i) {
                auto [node, parent] = q.front();
                q.pop();
                current_level.push_back({node->val, parent});
                
                if (node->val == B) {
                    found = true;
                    target_parent = parent;
                }
                
                if (node->left) {
                    q.push({node->left, node});
                }
                if (node->right) {
                    q.push({node->right, node});
                }
            }
            
            if (found) {
                for (auto [val, parent] : current_level) {
                    if (parent != target_parent && val != B) {
                        cousins.push_back(val);
                    }
                }
                break;
            }
        }
        
        return cousins;
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
    public ArrayList<Integer> solve(TreeNode A, int B) {
        ArrayList<Integer> cousins = new ArrayList<>();
        if (A == null) return cousins;
        
        Queue<Pair<TreeNode, TreeNode>> queue = new LinkedList<>();
        queue.add(new Pair<>(A, null));
        boolean found = false;
        TreeNode targetParent = null;
        
        while (!queue.isEmpty()) {
            int levelSize = queue.size();
            List<Pair<Integer, TreeNode>> currentLevel = new ArrayList<>();
            
            for (int i = 0; i < levelSize; i++) {
                Pair<TreeNode, TreeNode> pair = queue.poll();
                TreeNode node = pair.getKey();
                TreeNode parent = pair.getValue();
                currentLevel.add(new Pair<>(node.val, parent));
                
                if (node.val == B) {
                    found = true;
                    targetParent = parent;
                }
                
                if (node.left != null) {
                    queue.add(new Pair<>(node.left, node));
                }
                if (node.right != null) {
                    queue.add(new Pair<>(node.right, node));
                }
            }
            
            if (found) {
                for (Pair<Integer, TreeNode> p : currentLevel) {
                    int val = p.getKey();
                    TreeNode parent = p.getValue();
                    if (parent != targetParent && val != B) {
                        cousins.add(val);
                    }
                }
                break;
            }
        }
        
        return cousins;
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
from collections import deque

# Definition for a binary tree node.
class TreeNode:
    def __init__(self, x):
        self.val = x
        self.left = None
        self.right = None

class Solution:
    # @param A : root node of tree
    # @param B : integer
    # @return a list of integers
    def solve(self, A, B):
        if not A:
            return []
        
        queue = deque()
        queue.append((A, None))  # (node, parent)
        found_level = -1
        target_parent = None
        cousins = []
        
        while queue:
            level_size = len(queue)
            current_level_nodes = []
            
            for _ in range(level_size):
                node, parent = queue.popleft()
                current_level_nodes.append((node.val, parent))
                
                if node.val == B:
                    found_level = 0
                    target_parent = parent
                
                if node.left:
                    queue.append((node.left, node))
                if node.right:
                    queue.append((node.right, node))
            
            if found_level == 0:
                # Collect cousins from current_level_nodes
                for val, parent in current_level_nodes:
                    if parent != target_parent and val != B:
                        cousins.append(val)
                break
            elif found_level != -1:
                found_level -= 1
        
        return cousins
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
