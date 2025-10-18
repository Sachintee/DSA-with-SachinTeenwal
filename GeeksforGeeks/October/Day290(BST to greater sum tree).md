---
title: "🌳 BST to Greater Sum Tree | GFG Solution 🔍"
keywords🏷️: ["🌳 binary search tree", "🔄 tree transformation", "📊 reverse inorder", "🎯 greater sum tree", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the BST to Greater Sum Tree problem: transform each node to contain sum of all greater nodes using reverse inorder traversal. 🚀"
date: 📅 2025-10-17
---

# *290. BST to Greater Sum Tree*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/bst-to-greater-sum-tree/1)

## **🧩 Problem Description**

Given the root of a **Binary Search Tree (BST)** with unique node values, transform it into a **greater sum tree** where each node contains the sum of all nodes greater than that node.

A greater sum tree is a modified BST where every node's value is replaced by the sum of all node values that are strictly greater than the current node's value in the original BST.


## Code(C++)
```cpp
class Solution {
public:
    void transformTree(Node* root) {
        int s = 0;
        function<void(Node*)> f = [&](Node* n) {
            if (!n) return;
            f(n->right);
            int temp = n->data;
            n->data = s;
            s += temp;
            f(n->left);
        };
        f(root);
    }
};
```

## Code (Java)

```java
class Solution {
    int s = 0;
    public void transformTree(Node root) {
        if (root == null) return;
        transformTree(root.right);
        int temp = root.data;
        root.data = s;
        s += temp;
        transformTree(root.left);
    }
}
```

## Code (Python)

```python
class Solution:
    def transformTree(self, root):
        self.s = 0
        def f(n):
            if not n: return
            f(n.right)
            temp = n.data
            n.data = self.s
            self.s += temp
            f(n.left)
        f(root)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
