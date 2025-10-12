---
title: "🍬 Distribute Candies | GFG Solution 🌳"
keywords🏷️: ["🍬 distribute candies", "🌳 binary tree", "🔄 DFS", "⚖️ balance calculation", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Distribute Candies in Binary Tree problem: find minimum moves to distribute candies such that each node has exactly one candy using post-order DFS traversal. 🚀"
date: 📅 2025-10-12
---

# *285. Distribute Candies*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/distribute-candies-in-a-binary-tree/1)

## **🧩 Problem Description**

You are given the root of a binary tree with `n` nodes, where each node contains a certain number of candies, and the total number of candies across all nodes is `n`. In one move, you can select any two adjacent nodes and transfer one candy from one node to the other. The transfer can occur between a parent and child in either direction.

The task is to determine the **minimum number of moves** required to ensure that every node in the tree has exactly one candy.

**Note:** The testcases are framed such that it is always possible to achieve a configuration in which every node has exactly one candy, after some moves.


## Code(C++)
```cpp
class Solution {
public:
    int distCandy(Node* root) {
        int moves = 0;
        function<int(Node*)> dfs = [&](Node* n) {
            if (!n) return 0;
            int bal = n->data - 1 + dfs(n->left) + dfs(n->right);
            moves += abs(bal);
            return bal;
        };
        dfs(root);
        return moves;
    }
};
```

## Code (Java)

```java
class Solution {
    int moves = 0;
    public int distCandy(Node root) {
        dfs(root);
        return moves;
    }
    int dfs(Node n) {
        if (n == null) return 0;
        int bal = n.data - 1 + dfs(n.left) + dfs(n.right);
        moves += Math.abs(bal);
        return bal;
    }
}
```

## Code (Python)

```python
class Solution:
    def distCandy(self, root):
        self.moves = 0
        def dfs(n):
            if not n: return 0
            bal = n.data - 1 + dfs(n.left) + dfs(n.right)
            self.moves += abs(bal)
            return bal
        dfs(root)
        return self.moves
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
