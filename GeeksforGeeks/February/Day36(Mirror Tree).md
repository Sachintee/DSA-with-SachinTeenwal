---
Difficulty: Easy  
Source: 160 Days of Problem Solving  
Tags:
  - Tree
---

# 🚀 _Day 36. Mirror Tree_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/tree-gfg-160/problem/mirror-tree)  

## 💡 **Problem Description:**

Given a binary tree, convert it into its **Mirror Tree** by swapping the left and right children of all non-leaf nodes.  


## Code(C++)
```cpp
class Solution {
public:
    void mirror(Node* node) {
        if (!node) return;
        mirror(node->left);
        mirror(node->right);
        swap(node->left, node->right);
    }
};
```

## Code (Java)

```java
class Solution {
    void mirror(Node node) {
        if (node == null) return;
        mirror(node.left);
        mirror(node.right);
        Node temp = node.left;
        node.left = node.right;
        node.right = temp;
    }
}
```

## Code (Python)

```python
class Solution:
    def mirror(self, root):
        if not root:
            return
        self.mirror(root.left)
        self.mirror(root.right)
        root.left, root.right = root.right, root.left
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
