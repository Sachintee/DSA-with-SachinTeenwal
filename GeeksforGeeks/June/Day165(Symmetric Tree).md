---
title: "🌳 Symmetric Tree | GFG Solution 🔍"
keywords🏷️: ["🌳 symmetric tree", "🔍 binary tree", "🪞 mirror image", "🌿 tree traversal", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Symmetric Tree problem: check if a binary tree is symmetric using recursive mirror comparison. 🚀"
date: 📅 2025-06-14
---

# *165. Symmetric Tree*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/symmetric-tree/1)

## **🧩 Problem Description**

Given the root of a **binary tree**, check whether it is **symmetric**, i.e., whether the tree is a mirror image of itself.

A binary tree is symmetric if the **left subtree** is a mirror reflection of the **right subtree**.


## Code(C++)
```cpp
class Solution {
  bool isSym(Node* a, Node* b){
    if(!a||!b) return a==b;
    if(a->data!=b->data) return false;
    return isSym(a->left,b->right)&&isSym(a->right,b->left);
  }
 public:
    bool isSymmetric(Node* r){
        return !r||isSym(r->left,r->right);
    }
};
```

## Code (Java)

```java
class Solution {
    boolean isSym(Node a, Node b){
        if(a==null||b==null) return a==b;
        if(a.data!=b.data) return false;
        return isSym(a.left,b.right)&&isSym(a.right,b.left);
    }
    public boolean isSymmetric(Node r){
        return r==null||isSym(r.left,r.right);
    }
}
```

## Code (Python)

```python
class Solution:
    def isSym(self,a,b):
        if not a or not b: return a is b
        if a.data!=b.data: return False
        return self.isSym(a.left,b.right) and self.isSym(a.right,b.left)
    def isSymmetric(self, root):
        return root is None or self.isSym(root.left,root.right)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
