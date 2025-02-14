---
Difficulty: Hard  
Source: 160 Days of Problem Solving  
Tags:
  - Tree
  - Binary Search Tree
---

# 🚀 _Day 45. Fixing Two nodes of a BST_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/tree-gfg-160/problem/fixed-two-nodes-of-a-bst)  

## 💡 **Problem Description:**

Given the root of a **Binary Search Tree (BST)**, where exactly **two nodes were swapped** by mistake, your task is to **fix (or correct) the BST** by swapping them back. The **structure of the tree should not change**.  


## Code(C++)
```cpp
class Solution {
public:
    void correctBST(Node* root) {
        Node *first = nullptr, *middle = nullptr, *last = nullptr, *prev = nullptr;
        function<void(Node*)> inorder = [&](Node* node) {
            if (!node) return;
            inorder(node->left);
            if (prev && node->data < prev->data) {
                if (!first) first = prev, middle = node;
                else last = node;
            }
            prev = node;
            inorder(node->right);
        };
        inorder(root);
        swap(first->data, last ? last->data : middle->data);
    }
};
```

## Code (Java)

```java
class Solution {
    Node first, middle, last, prev;

    void inorder(Node root) {
        if (root == null) return;
        inorder(root.left);
        if (prev != null && root.data < prev.data) {
            if (first == null) {
                first = prev;
                middle = root;
            } else {
                last = root;
            }
        }
        prev = root;
        inorder(root.right);
    }

    void correctBST(Node root) {
        first = middle = last = prev = null;
        inorder(root);
        int temp = first.data;
        first.data = (last != null) ? last.data : middle.data;
        if (last != null) last.data = temp;
        else middle.data = temp;
    }
}
```

## Code (Python)

```python
class Solution:
    def correctBST(self, root):
        self.first = self.middle = self.last = self.prev = None

        def inorder(node):
            if not node:
                return
            inorder(node.left)
            if self.prev and node.data < self.prev.data:
                if not self.first:
                    self.first, self.middle = self.prev, node
                else:
                    self.last = node
            self.prev = node
            inorder(node.right)

        inorder(root)
        self.first.data, (self.last or self.middle).data = (self.last or self.middle).data, self.first.data
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
