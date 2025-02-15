---
Difficulty: Easy  
Source: 160 Days of Problem Solving  
Tags:
  - Tree
  - Binary Search Tree
---

# 🚀 _Day 46. Lowest Common Ancestor in a BST_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/tree-gfg-160/problem/lowest-common-ancestor-in-a-bst)  

## 💡 **Problem Description:**

Given a **Binary Search Tree (BST)** with **unique values** and two nodes `n1` and `n2` (where `n1 != n2`), find the **Lowest Common Ancestor (LCA)** of the two given nodes in the BST.  

The **LCA** is the lowest node in the BST that has both `n1` and `n2` as **descendants** (a node is also considered its own descendant).  


## Code(C++)
```cpp
class Solution {
public:
    Node* LCA(Node* root, Node* n1, Node* n2) {
        while (root && (root->data > max(n1->data, n2->data) || root->data < min(n1->data, n2->data)))
            root = (root->data > n1->data) ? root->left : root->right;
        return root;
    }
};
```

## Code (Java)

```java
class Solution {
    Node LCA(Node root, Node n1, Node n2) {
        while (root != null && (root.data > Math.max(n1.data, n2.data) || root.data < Math.min(n1.data, n2.data)))
            root = (root.data > n1.data) ? root.left : root.right;
        return root;
    }
}
```

## Code (Python)

```python
class Solution:
    def LCA(self, root, n1, n2):
        while root and (root.data > max(n1.data, n2.data) or root.data < min(n1.data, n2.data)):
            root = root.left if root.data > n1.data else root.right
        return root
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
