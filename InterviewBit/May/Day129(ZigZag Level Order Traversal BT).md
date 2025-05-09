--- ❤️ ---

# 🚀 _Day 129. ZigZag Level Order Traversal BT_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/zigzag-level-order-traversal-bt/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <queue>
#include <deque>
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
    vector<vector<int>> zigzagLevelOrder(TreeNode* root) {
        vector<vector<int>> result;
        if (!root) return result;
        
        queue<TreeNode*> q;
        q.push(root);
        bool left_to_right = true;
        
        while (!q.empty()) {
            int level_size = q.size();
            deque<int> current_level;
            
            for (int i = 0; i < level_size; ++i) {
                TreeNode* node = q.front();
                q.pop();
                
                if (left_to_right) {
                    current_level.push_back(node->val);
                } else {
                    current_level.push_front(node->val);
                }
                
                if (node->left) q.push(node->left);
                if (node->right) q.push(node->right);
            }
            
            result.push_back(vector<int>(current_level.begin(), current_level.end()));
            left_to_right = !left_to_right;
        }
        
        return result;
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
    public ArrayList<ArrayList<Integer>> zigzagLevelOrder(TreeNode A) {
        ArrayList<ArrayList<Integer>> result = new ArrayList<>();
        if (A == null) return result;
        
        Queue<TreeNode> queue = new LinkedList<>();
        queue.add(A);
        boolean leftToRight = true;
        
        while (!queue.isEmpty()) {
            int levelSize = queue.size();
            LinkedList<Integer> currentLevel = new LinkedList<>();
            
            for (int i = 0; i < levelSize; i++) {
                TreeNode node = queue.poll();
                
                if (leftToRight) {
                    currentLevel.addLast(node.val);
                } else {
                    currentLevel.addFirst(node.val);
                }
                
                if (node.left != null) queue.add(node.left);
                if (node.right != null) queue.add(node.right);
            }
            
            result.add(new ArrayList<>(currentLevel));
            leftToRight = !leftToRight;
        }
        
        return result;
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
    # @return a list of list of integers
    def zigzagLevelOrder(self, A):
        if not A:
            return []
        
        result = []
        queue = deque([A])
        left_to_right = True
        
        while queue:
            level_size = len(queue)
            current_level = deque()
            
            for _ in range(level_size):
                node = queue.popleft()
                
                if left_to_right:
                    current_level.append(node.val)
                else:
                    current_level.appendleft(node.val)
                
                if node.left:
                    queue.append(node.left)
                if node.right:
                    queue.append(node.right)
            
            result.append(list(current_level))
            left_to_right = not left_to_right
        
        return result
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
