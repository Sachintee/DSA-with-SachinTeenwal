---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Tree
---

# 🚀 _Day 40. Maximum path sum from any node_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/tree-gfg-160/problem/maximum-path-sum-from-any-node)

## 💡 **Problem Description:**

Given a binary tree, the task is to find the maximum path sum. The path may start and end at any node in the tree.

## Code(C++)
```cpp
class Solution {
    int dfs(Node* r, int& res) {
        if (!r) return 0;
        int l = max(0, dfs(r->left, res)), rgt = max(0, dfs(r->right, res));
        res = max(res, l + rgt + r->data);
        return max(l, rgt) + r->data;
    }
public:
    int findMaxSum(Node* root) {
        int res = INT_MIN;
        dfs(root, res);
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    int dfs(Node r, int[] res) {
        if (r == null) return 0;
        int l = Math.max(0, dfs(r.left, res)), rgt = Math.max(0, dfs(r.right, res));
        res[0] = Math.max(res[0], l + rgt + r.data);
        return Math.max(l, rgt) + r.data;
    }
    int findMaxSum(Node root) {
        int[] res = {Integer.MIN_VALUE};
        dfs(root, res);
        return res[0];
    }
}
```

## Code (Python)

```python
class Solution:
    def findMaxSum(self, root):
        def dfs(node):
            if not node: return 0
            l = max(0, dfs(node.left))
            r = max(0, dfs(node.right))
            nonlocal res
            res = max(res, l + r + node.data)
            return max(l, r) + node.data
        res = float('-inf')
        dfs(root)
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
