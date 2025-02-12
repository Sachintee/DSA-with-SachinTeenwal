---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Tree
  - Binary Search Tree
---

# 🚀 _Day 43. k-th Smallest in BST_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/tree-gfg-160/problem/find-k-th-smallest-element-in-bst)  



## 💡 **Problem Description:**

Given a **Binary Search Tree (BST)** and an integer **k**, the task is to find the **k-th smallest element** in the BST.  
If there is **no k-th smallest element** present, return `-1`.  

## Code(C++)
```cpp
class Solution {
  public:
    int kthSmallest(Node* root, int k) {
        while (root) {
            if (!root->left) {
                if (--k == 0) return root->data;
                root = root->right;
            } else {
                Node* pre = root->left;
                while (pre->right && pre->right != root) pre = pre->right;
                if (!pre->right) {
                    pre->right = root;
                    root = root->left;
                } else {
                    pre->right = NULL;
                    if (--k == 0) return root->data;
                    root = root->right;
                }
            }
        }
        return -1;
    }
};
```

## Code (Java)

```java
class Solution {
    public int kthSmallest(Node root, int k) {
        while (root != null) {
            if (root.left == null) {
                if (--k == 0) return root.data;
                root = root.right;
            } else {
                Node pre = root.left;
                while (pre.right != null && pre.right != root) pre = pre.right;
                if (pre.right == null) {
                    pre.right = root;
                    root = root.left;
                } else {
                    pre.right = null;
                    if (--k == 0) return root.data;
                    root = root.right;
                }
            }
        }
        return -1;
    }
}
```

## Code (Python)

```python
class Solution:
    def kthSmallest(self, root, k):
        while root:
            if not root.left:
                k -= 1
                if k == 0:
                    return root.data
                root = root.right
            else:
                pre = root.left
                while pre.right and pre.right != root:
                    pre = pre.right
                if not pre.right:
                    pre.right = root
                    root = root.left
                else:
                    pre.right = None
                    k -= 1
                    if k == 0:
                        return root.data
                    root = root.right
        return -1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
