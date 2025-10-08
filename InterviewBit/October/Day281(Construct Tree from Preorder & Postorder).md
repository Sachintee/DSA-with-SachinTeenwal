---
title: "🌲 Construct Tree from Preorder & Postorder | GFG Solution 🔍"
keywords🏷️: ["🌲 binary tree construction", "🔍 tree traversal", "📍 preorder postorder", "📈 recursion", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Construct Tree from Preorder & Postorder problem: build a full binary tree from preorder and postorder traversals using recursive approach with optimized lookups. 🚀"
date: 📅 2025-10-08
---

# *281. Construct Tree from Preorder & Postorder*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/construct-tree-from-preorder-postorder/1)

## **🧩 Problem Description**

Given two arrays `pre[]` and `post[]` that represent the preorder and postorder traversals of a full binary tree, your task is to construct the binary tree and return its root.

A **full binary tree** is a binary tree where every node has either 0 or 2 children. The preorder and postorder traversals contain unique values, and every value present in the preorder traversal is also found in the postorder traversal.


## Code(C++)
```cpp
class Solution {
public:
    int idx = 0;
    Node* constructTree(vector<int>& pre, vector<int>& post) {
        return build(pre, post, 0, post.size() - 1);
    }
    Node* build(vector<int>& pre, vector<int>& post, int l, int r) {
        Node* root = new Node(pre[idx++]);
        
        if (l != r && idx < pre.size()) {
            int pos = l;
            while (post[pos] != pre[idx]) pos++;
            
            root->left  = build(pre, post, l, pos);
            root->right = build(pre, post, pos + 1, r - 1);
        }
        return root;
    }
};
```

## Code (Java)

```java
class Solution {
    int idx = 0;
    public Node constructTree(int[] pre, int[] post) {
        return build(pre, post, 0, post.length - 1);
    }
    
    Node build(int[] pre, int[] post, int l, int r) {
        Node root = new Node(pre[idx++]);
        if (l != r && idx < pre.length) {
            int pos = l;
            while (post[pos] != pre[idx]) pos++;
            root.left = build(pre, post, l, pos);
            root.right = build(pre, post, pos + 1, r - 1);
        }
        return root;
    }
}
```

## Code (Python)

```python
class Solution:
    def constructTree(self, pre, post):
        self.idx = 0
        return self.build(pre, post, 0, len(post) - 1)
    
    def build(self, pre, post, l, r):
        root = Node(pre[self.idx])
        self.idx += 1
        if l != r and self.idx < len(pre):
            pos = post.index(pre[self.idx], l, r + 1)
            root.left = self.build(pre, post, l, pos)
            root.right = self.build(pre, post, pos + 1, r - 1)
        return root
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
