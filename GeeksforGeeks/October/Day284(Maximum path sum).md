---
title: "🌳 Maximum Path Sum | GFG Solution 🔍"
keywords🏷️: ["🌳 binary tree", "🔍 path sum", "📍 recursion", "📈 DFS", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Maximum Path Sum problem: find maximum sum path between any two nodes in a binary tree using recursive DFS technique. 🚀"
date: 📅 2025-10-11
---

# *284. Maximum Path Sum*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/maximum-path-sum-from-any-node/1)

## **🧩 Problem Description**

You are given the `root` of a binary tree. Your task is to find the **maximum path sum**. The path may start and end at **any node** in the tree.

A path is defined as any sequence of nodes from some starting node to any node in the tree along the parent-child connections. The path must contain at least one node and does not need to go through the root.


## Code(C++)
```cpp
class Solution {
public:
    int findMaxSum(Node *root) {
        int res = INT_MIN;
        dfs(root, res);
        return res;
    }
    
    int dfs(Node *node, int &res) {
        if (!node) return 0;
        int l = max(0, dfs(node->left, res));
        int r = max(0, dfs(node->right, res));
        res = max(res, node->data + l + r);
        return node->data + max(l, r);
    }
};
```

## Code (Java)

```java
class Solution {
    int res;
    
    int findMaxSum(Node root) {
        res = Integer.MIN_VALUE;
        dfs(root);
        return res;
    }
    
    int dfs(Node node) {
        if (node == null) return 0;
        int l = Math.max(0, dfs(node.left));
        int r = Math.max(0, dfs(node.right));
        res = Math.max(res, node.data + l + r);
        return node.data + Math.max(l, r);
    }
}
```

## Code (Python)

```python
class Solution:
    def findMaxSum(self, root): 
        self.res = float('-inf')
        
        def dfs(node):
            if not node: return 0
            l = max(0, dfs(node.left))
            r = max(0, dfs(node.right))
            self.res = max(self.res, node.data + l + r)
            return node.data + max(l, r)
        
        dfs(root)
        return self.res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
