--- ❤️ ---

# 🚀 _Day 277. Next Pointer Binary Tree_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/next-pointer-binary-tree/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    void connect(TreeLinkNode *root) {
        if (!root) return;
        
        TreeLinkNode* levelStart = root;
        
        while (levelStart) {
            TreeLinkNode* current = levelStart;
            
            // Process current level
            while (current) {
                if (current->left) {
                    current->left->next = current->right;
                }
                if (current->right && current->next) {
                    current->right->next = current->next->left;
                }
                current = current->next;
            }
            
            // Move to next level
            levelStart = levelStart->left;
        }
    }
};
```

## Code (Java)

```java
public class Solution {
    public void connect(TreeLinkNode root) {
        if (root == null) return;
        
        TreeLinkNode levelStart = root;
        
        while (levelStart != null) {
            TreeLinkNode current = levelStart;
            
            // Process current level
            while (current != null) {
                if (current.left != null) {
                    current.left.next = current.right;
                }
                if (current.right != null && current.next != null) {
                    current.right.next = current.next.left;
                }
                current = current.next;
            }
            
            // Move to next level
            levelStart = levelStart.left;
        }
    }
}
```

## Code (Python)

```python
# Definition for a  binary tree node
# class TreeLinkNode:
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None
#         self.next = None

class Solution:
    # @param root, a tree node
    # @return nothing
    def connect(self, root):
        if not root:
            return
        
        # Start with the root node
        current_level_start = root
        
        # Process each level
        while current_level_start and current_level_start.left:
            current = current_level_start
            
            # Connect all nodes at current level
            while current:
                # Connect left child to right child
                current.left.next = current.right
                
                # Connect right child to next node's left child (if exists)
                if current.next:
                    current.right.next = current.next.left
                
                # Move to next node in current level
                current = current.next
            
            # Move to next level
            current_level_start = current_level_start.left
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
