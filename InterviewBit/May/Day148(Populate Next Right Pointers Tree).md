--- ❤️ ---

# 🚀 _Day 148. Populate Next Right Pointers Tree_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/populate-next-right-pointers-tree/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
/**
 * Definition for binary tree with next pointer.
 * struct TreeLinkNode {
 *  int val;
 *  TreeLinkNode *left, *right, *next;
 *  TreeLinkNode(int x) : val(x), left(NULL), right(NULL), next(NULL) {}
 * };
 */
class Solution {
public:
    void connect(TreeLinkNode *root) {
        if (!root) return;
        
        TreeLinkNode *dummy = new TreeLinkNode(0);
        TreeLinkNode *prev = dummy;
        TreeLinkNode *current = root;
        
        while (current) {
            if (current->left) {
                prev->next = current->left;
                prev = prev->next;
            }
            if (current->right) {
                prev->next = current->right;
                prev = prev->next;
            }
            current = current->next;
            if (!current) {
                current = dummy->next;
                dummy->next = NULL;
                prev = dummy;
            }
        }
        
        delete dummy;
    }
};
```

## Code (Java)

```java
/**
 * Definition for binary tree with next pointer.
 * public class TreeLinkNode {
 *     int val;
 *     TreeLinkNode left, right, next;
 *     TreeLinkNode(int x) { val = x; }
 * }
 */
public class Solution {
    public void connect(TreeLinkNode root) {
        if (root == null) return;
        
        TreeLinkNode dummy = new TreeLinkNode(0);
        TreeLinkNode prev = dummy;
        TreeLinkNode current = root;
        
        while (current != null) {
            if (current.left != null) {
                prev.next = current.left;
                prev = prev.next;
            }
            if (current.right != null) {
                prev.next = current.right;
                prev = prev.next;
            }
            current = current.next;
            if (current == null) {
                current = dummy.next;
                dummy.next = null;
                prev = dummy;
            }
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
        
        dummy = TreeLinkNode(0)
        prev = dummy
        current = root
        
        while current:
            if current.left:
                prev.next = current.left
                prev = prev.next
            if current.right:
                prev.next = current.right
                prev = prev.next
            current = current.next
            if not current:
                current = dummy.next
                dummy.next = None
                prev = dummy
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
