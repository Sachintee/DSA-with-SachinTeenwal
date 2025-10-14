---
title: "🌳 Sum of Nodes in BST Range | GFG Solution 🔍"
keywords🏷️: ["🌳 binary search tree", "🔍 range sum", "🎯 BST traversal", "📊 tree algorithms", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Sum of Nodes in BST Range problem: efficiently calculate sum of all nodes within a given range using BST properties. 🚀"
date: 📅 2025-10-14
---

# *287. Sum of Nodes in BST Range*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/range-sum-of-bst/1)

## **🧩 Problem Description**

You are given the root of a **Binary Search Tree** and two integers `l` and `r`. Your task is to find the **sum of all nodes** that lie between `l` and `r`, including both `l` and `r`.

A Binary Search Tree (BST) is a binary tree where for each node, all values in the left subtree are less than the node's value, and all values in the right subtree are greater than the node's value. This property allows efficient searching and range queries.


## Code(C++)
```cpp
class Solution {
public:
    int nodeSum(Node* root, int l, int r) {
        if (!root) return 0;
        if (root->data < l) return nodeSum(root->right, l, r);
        if (root->data > r) return nodeSum(root->left, l, r);
        return root->data + nodeSum(root->left, l, r) + nodeSum(root->right, l, r);
    }
};
```

## Code (Java)

```java
class Solution {
    public int nodeSum(Node root, int l, int r) {
        if (root == null) return 0;
        if (root.data < l) return nodeSum(root.right, l, r);
        if (root.data > r) return nodeSum(root.left, l, r);
        return root.data + nodeSum(root.left, l, r) + nodeSum(root.right, l, r);
    }
}
```

## Code (Python)

```python
class Solution:
    def nodeSum(self, root, l, r):
        if not root: return 0
        if root.data < l: return self.nodeSum(root.right, l, r)
        if root.data > r: return self.nodeSum(root.left, l, r)
        return root.data + self.nodeSum(root.left, l, r) + self.nodeSum(root.right, l, r)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
