# *150. Closest Neighbour in BST*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/closest-neighbor-in-bst/1)

## **🧩 Problem Description**

Given the root of a Binary Search Tree and a value `k`, find the **greatest node value** in the tree that is **less than or equal to** `k`. If no such node exists, return `-1`.


## Code(C++)
```cpp
class Solution {
  public:
    int findMaxFork(Node* root, int k) {
        int res = -1;
        while (root) {
            if (root->data == k) return k;
            if (root->data < k) {
                res = root->data;
                root = root->right;
            } else {
                root = root->left;
            }
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public int findMaxFork(Node root, int k) {
        int res = -1;
        while (root != null) {
            if (root.data == k) return k;
            if (root.data < k) {
                res = root.data;
                root = root.right;
            } else {
                root = root.left;
            }
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def findMaxFork(self, root, k):
        res = -1
        while root:
            if root.data == k:
                return k
            if root.data < k:
                res = root.data
                root = root.right
            else:
                root = root.left
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
