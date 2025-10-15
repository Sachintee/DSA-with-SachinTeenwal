---
title: "🌳 Kth Smallest Element in BST | GFG Solution 🔍"
keywords🏷️: ["🌳 binary search tree", "🔍 inorder traversal", "📍 iterative stack", "📈 tree traversal", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Kth Smallest Element in BST problem: find the kth smallest element in a binary search tree using iterative inorder traversal with stack. 🚀"
date: 📅 2025-10-15
---

# *288. Kth Smallest Element in BST*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/find-k-th-smallest-element-in-bst/1)

## **🧩 Problem Description**

Given the root of a **Binary Search Tree (BST)** and an integer `k`, the task is to find the **kth smallest element** in the BST. If there is no kth smallest element present, return `-1`.

A BST is a tree where for each node, all elements in the left subtree are smaller and all elements in the right subtree are greater. An inorder traversal of a BST yields elements in sorted (ascending) order.


## Code(C++)
```cpp
class Solution {
public:
    int kthSmallest(Node *root, int k) {
        stack<Node*> s;
        Node* n = root;
        int c = 0;
        while (n || !s.empty()) {
            while (n) {
                s.push(n);
                n = n->left;
            }
            n = s.top(); s.pop();
            if (++c == k) return n->data;
            n = n->right;
        }
        return -1;
    }
};
```

## Code (Java)

```java
class Solution {
    public int kthSmallest(Node root, int k) {
        Stack<Node> s = new Stack<>();
        Node n = root;
        int c = 0;
        while (n != null || !s.isEmpty()) {
            while (n != null) {
                s.push(n);
                n = n.left;
            }
            n = s.pop();
            if (++c == k) return n.data;
            n = n.right;
        }
        return -1;
    }
}
```

## Code (Python)

```python
class Solution:
    def kthSmallest(self, root, k): 
        s, n, c = [], root, 0
        while n or s:
            while n:
                s.append(n)
                n = n.left
            n = s.pop()
            c += 1
            if c == k: return n.data
            n = n.right
        return -1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
