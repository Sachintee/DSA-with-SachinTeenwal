---
title: "🌳 BST with Dead End | GFG Solution 🚧"
keywords🏷️: ["🌳 BST", "🚧 dead end", "🧠 recursion", "📘 GFG", "✅ binary tree", "🔍 DFS", "🧬 tree traversal", "📚 DSA", "🏁 competitive programming"]
description: "✅ GFG solution to BST with Dead End: detect if a BST has any dead-end node where no more insertions are possible while maintaining BST properties. 🚀"
date: 📅 2025-06-09
---

# *160. BST with Dead End*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/check-whether-bst-contains-dead-end/1)


## **🧩 Problem Description**

You are given a **Binary Search Tree (BST)** that contains **only unique positive integers greater than 0**. A **dead end** is a **leaf node** such that no further node can be inserted under it while still maintaining the BST property and constraint that node values must be **> 0**.

Your task is to determine whether the BST contains any such **dead end**.



## Code(C++)
```cpp
class Solution {
  public:
    bool dfs(Node* root, int l, int r) {
        if (!root) return false;
        if (!root->left && !root->right && l == r) return true;
        return dfs(root->left, l, root->data - 1) || dfs(root->right, root->data + 1, r);
    }
    bool isDeadEnd(Node* root) {
        return dfs(root, 1, INT_MAX);
    }
};
```

## Code (Java)

```java
class Solution {
    boolean dfs(Node root, int l, int r) {
        if (root == null) return false;
        if (root.left == null && root.right == null && l == r) return true;
        return dfs(root.left, l, root.data - 1) || dfs(root.right, root.data + 1, r);
    }
    
    public boolean isDeadEnd(Node root) {
        return dfs(root, 1, Integer.MAX_VALUE);
    }
}
```

## Code (Python)

```python
class Solution:
    def dfs(self, root, l, r):
        if not root: return False
        if not root.left and not root.right and l == r: return True
        return self.dfs(root.left, l, root.data - 1) or self.dfs(root.right, root.data + 1, r)

    def isDeadEnd(self, root):
        return self.dfs(root, 1, float('inf'))
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
