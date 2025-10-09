---
title: "🌳 Postorder Traversal | GFG Solution 🔍"  
keywords🏷️: ["🌳 binary tree", "🔄 postorder traversal", "🔍 morris traversal", "📊 tree traversal", "📘 GFG", "🏁 competitive programming", "📚 DSA"]  
description: "✅ GFG solution to the Postorder Traversal problem: traverse binary tree in postorder using Morris Traversal technique with O(1) space complexity. 🚀"  
date: 📅 2025-10-09  
---

# *282. Postorder Traversal*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/postorder-traversal/1)

## **🧩 Problem Description**

Given the root of a Binary Tree, your task is to return its **Postorder Traversal**.

A postorder traversal first visits the left child (including its entire subtree), then visits the right child (including its entire subtree), and finally visits the node itself.

## Code(C++)
```cpp
class Solution {
public:
    vector<int> postOrder(Node *root) {
        vector<int> res;
        Node *curr = root;
        while (curr) {
            if (!curr->right) {
                res.push_back(curr->data);
                curr = curr->left;
            } else {
                Node *pred = curr->right;
                while (pred->left && pred->left != curr) pred = pred->left;
                if (!pred->left) {
                    res.push_back(curr->data);
                    pred->left = curr;
                    curr = curr->right;
                } else {
                    pred->left = NULL;
                    curr = curr->left;
                }
            }
        }
        reverse(res.begin(), res.end());
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<Integer> postOrder(Node root) {
        ArrayList<Integer> res = new ArrayList<>();
        Node curr = root;
        while (curr != null) {
            if (curr.right == null) {
                res.add(curr.data);
                curr = curr.left;
            } else {
                Node pred = curr.right;
                while (pred.left != null && pred.left != curr) pred = pred.left;
                if (pred.left == null) {
                    res.add(curr.data);
                    pred.left = curr;
                    curr = curr.right;
                } else {
                    pred.left = null;
                    curr = curr.left;
                }
            }
        }
        Collections.reverse(res);
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def postOrder(self, root):
        res = []
        curr = root
        while curr:
            if not curr.right:
                res.append(curr.data)
                curr = curr.left
            else:
                pred = curr.right
                while pred.left and pred.left != curr:
                    pred = pred.left
                if not pred.left:
                    res.append(curr.data)
                    pred.left = curr
                    curr = curr.right
                else:
                    pred.left = None
                    curr = curr.left
        res.reverse()
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
