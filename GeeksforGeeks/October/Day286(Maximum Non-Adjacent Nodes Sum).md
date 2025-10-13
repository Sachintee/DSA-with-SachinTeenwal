---
title: "🌳 Maximum Non-Adjacent Nodes Sum | GFG Solution 🔍"
keywords🏷️: ["🌳 binary tree", "🔍 dynamic programming", "📍 tree dp", "📈 recursion", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Maximum Non-Adjacent Nodes Sum problem: find maximum sum of nodes in a binary tree where no two adjacent nodes are selected using dynamic programming on trees. 🚀"
date: 📅 2025-10-13
---

# *286. Maximum Non-Adjacent Nodes Sum*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/maximum-sum-of-non-adjacent-nodes/1)

## **🧩 Problem Description**

Given the root of a binary tree with integer values, your task is to select a subset of nodes such that the sum of their values is maximized, with the condition that **no two selected nodes are directly connected**. That is, if a node is included in the subset, neither its parent nor its children can be included.

A node and its immediate parent or children form adjacent pairs in the tree structure. The goal is to maximize the sum while respecting this non-adjacency constraint.


## Code(C++)
```cpp
class Solution {
public:
    int getMaxSum(Node* root) {
        function<pair<int,int>(Node*)> dfs = [&](Node* node) -> pair<int,int> {
            if (!node) return {0, 0};
            auto [li, le] = dfs(node->left);
            auto [ri, re] = dfs(node->right);
            return {node->data + le + re, max(li, le) + max(ri, re)};
        };
        auto [inc, exc] = dfs(root);
        return max(inc, exc);
    }
};
```

## Code (Java)

```java
class Solution {
    public int getMaxSum(Node root) {
        int[] res = helper(root);
        return Math.max(res[0], res[1]);
    }
    private int[] helper(Node node) {
        if (node == null) return new int[]{0, 0};
        int[] l = helper(node.left);
        int[] r = helper(node.right);
        int inc = node.data + l[1] + r[1];
        int exc = Math.max(l[0], l[1]) + Math.max(r[0], r[1]);
        return new int[]{inc, exc};
    }
}
```

## Code (Python)

```python
class Solution:
    def getMaxSum(self, root):
        def helper(node):
            if not node: return (0, 0)
            l = helper(node.left)
            r = helper(node.right)
            inc = node.data + l[1] + r[1]
            exc = max(l) + max(r)
            return (inc, exc)
        return max(helper(root))
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
