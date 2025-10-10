---
title: "🌲 ZigZag Tree Traversal | GFG Solution 🔍"
keywords🏷️: ["🌲 binary tree", "🔍 level order", "📍 zigzag traversal", "📈 BFS", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the ZigZag Tree Traversal problem: perform level order traversal in alternating left-to-right and right-to-left directions using efficient queue-based techniques. 🚀"
date: 📅 2025-10-10
---

# *283. ZigZag Tree Traversal*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/zigzag-tree-traversal/1)

## **🧩 Problem Description**

Given the root of a binary tree, you need to perform a **zigzag level order traversal**. In this traversal:
- **Odd-numbered levels** (1st, 3rd, 5th, etc.) are traversed from **left to right**.
- **Even-numbered levels** (2nd, 4th, 6th, etc.) are traversed from **right to left**.

Return the nodes in the order they appear during this zigzag traversal.


## Code(C++)
```cpp
class Solution {
public:
    vector<int> zigZagTraversal(Node* root) {
        vector<int> res;
        if (!root) return res;
        queue<Node*> q;
        q.push(root);
        bool ltr = true;
        while (!q.empty()) {
            int sz = q.size();
            vector<int> lvl(sz);
            for (int i = 0; i < sz; i++) {
                Node* node = q.front();
                q.pop();
                int idx = ltr ? i : sz - 1 - i;
                lvl[idx] = node->data;
                if (node->left) q.push(node->left);
                if (node->right) q.push(node->right);
            }
            ltr = !ltr;
            res.insert(res.end(), lvl.begin(), lvl.end());
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    ArrayList<Integer> zigZagTraversal(Node root) {
        ArrayList<Integer> res = new ArrayList<>();
        if (root == null) return res;
        Queue<Node> q = new LinkedList<>();
        q.add(root);
        boolean ltr = true;
        while (!q.isEmpty()) {
            int sz = q.size();
            Integer[] lvl = new Integer[sz];
            for (int i = 0; i < sz; i++) {
                Node node = q.poll();
                int idx = ltr ? i : sz - 1 - i;
                lvl[idx] = node.data;
                if (node.left != null) q.add(node.left);
                if (node.right != null) q.add(node.right);
            }
            ltr = !ltr;
            Collections.addAll(res, lvl);
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def zigZagTraversal(self, root):
        res = []
        if not root: return res
        q = deque([root])
        ltr = True
        while q:
            sz = len(q)
            lvl = [0] * sz
            for i in range(sz):
                node = q.popleft()
                idx = i if ltr else sz - 1 - i
                lvl[idx] = node.data
                if node.left: q.append(node.left)
                if node.right: q.append(node.right)
            ltr = not ltr
            res.extend(lvl)
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
