---
Difficulty: Easy  
Source: 160 Days of Problem Solving  
Tags:
  - Tree
  - Binary Search Tree
---

# 🚀 _Day 42. Check for BST_ 🧠

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/tree-gfg-160/problem/check-for-bst)  

## 💡 **Problem Description:**

Given the root of a binary tree, check whether it is a **Binary Search Tree (BST)** or not.  


## Code(C++)
```cpp
class Solution {
public:
    bool isBST(Node* root, int min = INT_MIN, int max = INT_MAX) {
        return !root || (root->data > min && root->data < max &&
                         isBST(root->left, min, root->data) &&
                         isBST(root->right, root->data, max));
    }
};
```

## Code (Java)

```java
class Solution {
    boolean isBST(Node root) {
        return isBST(root, Integer.MIN_VALUE, Integer.MAX_VALUE);
    }

    boolean isBST(Node node, int min, int max) {
        return node == null || (node.data > min && node.data < max &&
                isBST(node.left, min, node.data) &&
                isBST(node.right, node.data, max));
    }
}
```

## Code (Python)

```python
class Solution:
    def isBST(self, root, min_val=float('-inf'), max_val=float('inf')):
        return not root or (min_val < root.data < max_val and
                            self.isBST(root.left, min_val, root.data) and
                            self.isBST(root.right, root.data, max_val))
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
