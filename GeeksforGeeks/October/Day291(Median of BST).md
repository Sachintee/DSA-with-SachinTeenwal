---
title: "🌳 Median of BST | GFG Solution 🔍"
keywords🏷️: ["🌳 binary search tree", "🔍 morris traversal", "📍 inorder traversal", "📈 median finding", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Median of BST problem: find median element in a BST using space-efficient Morris Traversal technique without recursion or stack. 🚀"
date: 📅 2025-10-18
---

# *291. Median of BST*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/median-of-bst/1)

## **🧩 Problem Description**

You are given the root of a **Binary Search Tree (BST)**. Your task is to find the **median** of the BST.

When the nodes of the BST are written in ascending order (inorder traversal) as V₁, V₂, V₃, …, Vₙ, where n is the total number of nodes:


## Code(C++)
```cpp
class Solution {
public:
    int findMedian(Node* root) {
        int n = 0, k = 0, med = -1;
        Node* c = root;
        while (c) {
            if (!c->left) { n++; c = c->right; }
            else {
                Node* p = c->left;
                while (p->right && p->right != c) p = p->right;
                if (!p->right) { p->right = c; c = c->left; }
                else { p->right = nullptr; n++; c = c->right; }
            }
        }
        k = (n + 1) / 2;
        c = root;
        while (c) {
            if (!c->left) {
                if (++med == k - 1) return c->data;
                c = c->right;
            } else {
                Node* p = c->left;
                while (p->right && p->right != c) p = p->right;
                if (!p->right) { p->right = c; c = c->left; }
                else {
                    p->right = nullptr;
                    if (++med == k - 1) return c->data;
                    c = c->right;
                }
            }
        }
        return -1;
    }
};
```

## Code (Java)

```java
class Solution {
    public int findMedian(Node root) {
        int n = 0, k = 0, med = -1;
        Node c = root;
        while (c != null) {
            if (c.left == null) { n++; c = c.right; }
            else {
                Node p = c.left;
                while (p.right != null && p.right != c) p = p.right;
                if (p.right == null) { p.right = c; c = c.left; }
                else { p.right = null; n++; c = c.right; }
            }
        }
        k = (n + 1) / 2;
        c = root;
        while (c != null) {
            if (c.left == null) {
                if (++med == k - 1) return c.data;
                c = c.right;
            } else {
                Node p = c.left;
                while (p.right != null && p.right != c) p = p.right;
                if (p.right == null) { p.right = c; c = c.left; }
                else {
                    p.right = null;
                    if (++med == k - 1) return c.data;
                    c = c.right;
                }
            }
        }
        return -1;
    }
}
```

## Code (Python)

```python
class Solution:
    def findMedian(self, root):
        n, c = 0, root
        while c:
            if not c.left:
                n += 1
                c = c.right
            else:
                p = c.left
                while p.right and p.right != c:
                    p = p.right
                if not p.right:
                    p.right = c
                    c = c.left
                else:
                    p.right = None
                    n += 1
                    c = c.right
        k, med, c = (n + 1) // 2, -1, root
        while c:
            if not c.left:
                med += 1
                if med == k - 1:
                    return c.data
                c = c.right
            else:
                p = c.left
                while p.right and p.right != c:
                    p = p.right
                if not p.right:
                    p.right = c
                    c = c.left
                else:
                    p.right = None
                    med += 1
                    if med == k - 1:
                        return c.data
                    c = c.right
        return -1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
