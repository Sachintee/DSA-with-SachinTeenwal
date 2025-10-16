---
title: "🌳 Remove BST Keys Outside Given Range | GFG Solution 🔍"
keywords🏷️: ["🌳 binary search tree", "🔍 BST trimming", "📍 recursion", "🔄 tree traversal", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to Remove BST Keys Outside Given Range: efficiently trim a BST to keep only nodes within a specified range using recursive DFS. 🚀"
date: 📅 2025-10-16
---

# *289. Remove BST Keys Outside Given Range*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/remove-bst-keys-outside-given-range/1)

## **🧩 Problem Description**

Given the root of a **Binary Search Tree (BST)** and two integers `l` and `r`, remove all the nodes whose values lie outside the range `[l, r]`.

**Note:** The modified tree should also be a BST and the sequence of the remaining nodes should not be changed.


## Code(C++)
```cpp
class Solution {
public:
    Node* removekeys(Node* root, int l, int r) {
        if (!root) return NULL;
        root->left = removekeys(root->left, l, r);
        root->right = removekeys(root->right, l, r);
        if (root->data < l) return root->right;
        if (root->data > r) return root->left;
        return root;
    }
};
```

## Code (Java)

```java
class Solution {
    Node removekeys(Node root, int l, int r) {
        if (root == null) return null;
        root.left = removekeys(root.left, l, r);
        root.right = removekeys(root.right, l, r);
        if (root.data < l) return root.right;
        if (root.data > r) return root.left;
        return root;
    }
}
```

## Code (Python)

```python
class Solution:
    def removekeys(self, root, l, r):
        if not root: return None
        root.left = self.removekeys(root.left, l, r)
        root.right = self.removekeys(root.right, l, r)
        if root.data < l: return root.right
        if root.data > r: return root.left
        return root
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
