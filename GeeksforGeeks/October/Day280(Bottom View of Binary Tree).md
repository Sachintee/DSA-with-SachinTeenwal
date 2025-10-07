---
title: "🌳 Bottom View of Binary Tree | GFG Solution 🔍"
keywords🏷️: ["🌳 binary tree", "🔍 bottom view", "📍 BFS traversal", "📈 horizontal distance", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
author: "✍️ Het Patel (Hunterdii)"
description: "✅ GFG solution to the Bottom View of Binary Tree problem: find nodes visible from bottom using level order traversal and horizontal distance tracking. 🚀"
date: 📅 2025-10-07
---

# *280. Bottom View of Binary Tree*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/bottom-view-of-binary-tree/1)

## **🧩 Problem Description**

You are given the root of a binary tree, and your task is to return its **bottom view**. The bottom view of a binary tree is the set of nodes visible when the tree is viewed from the bottom.

**Note:** If there are multiple bottom-most nodes for a horizontal distance from the root, then the latter one in the level order traversal is considered.

## Code(C++)
```cpp
class Solution {
public:
    vector<int> bottomView(Node* root) {
        if (!root) return {};
        map<int, int> m;
        queue<pair<Node*, int>> q;
        q.push({root, 0});
        while (!q.empty()) {
            auto [node, hd] = q.front();
            q.pop();
            m[hd] = node->data;
            if (node->left) q.push({node->left, hd - 1});
            if (node->right) q.push({node->right, hd + 1});
        }
        vector<int> res;
        for (auto& [k, v] : m) res.push_back(v);
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<Integer> bottomView(Node root) {
        ArrayList<Integer> res = new ArrayList<>();
        if (root == null) return res;
        TreeMap<Integer, Integer> map = new TreeMap<>();
        Queue<Pair> q = new LinkedList<>();
        q.add(new Pair(root, 0));
        while (!q.isEmpty()) {
            Pair p = q.poll();
            map.put(p.hd, p.node.data);
            if (p.node.left != null) q.add(new Pair(p.node.left, p.hd - 1));
            if (p.node.right != null) q.add(new Pair(p.node.right, p.hd + 1));
        }
        for (int val : map.values()) res.add(val);
        return res;
    }
    class Pair {
        Node node;
        int hd;
        Pair(Node n, int h) { node = n; hd = h; }
    }
}
```

## Code (Python)

```python
class Solution:
    def bottomView(self, root):
        if not root: return []
        d = {}
        q = deque([(root, 0)])
        while q:
            node, hd = q.popleft()
            d[hd] = node.data
            if node.left: q.append((node.left, hd - 1))
            if node.right: q.append((node.right, hd + 1))
        return [d[k] for k in sorted(d)]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
