# *139. Predecessor and Successor*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/predecessor-and-successor/1)


## **🧩 Problem Description**

Given the root of a Binary Search Tree (BST) and an integer key, find the inorder predecessor and successor of the key in the BST.

* The **predecessor** is the largest value in the BST smaller than the key.
* The **successor** is the smallest value in the BST larger than the key.
* If predecessor or successor does not exist, return `NULL`.


## Code(C++)
```cpp
class Solution {
  public:
    vector<Node*> findPreSuc(Node* root, int key) {
        Node *pre = nullptr, *suc = nullptr;
        Node* curr = root;
        while (curr) {
            if (curr->data < key) {
                pre = curr;
                curr = curr->right;
            } else curr = curr->left;
        }
        curr = root;
        while (curr) {
            if (curr->data > key) {
                suc = curr;
                curr = curr->left;
            } else curr = curr->right;
        }
        return {pre, suc};
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<Node> findPreSuc(Node root, int key) {
        Node pre = null, suc = null, curr = root;
        while (curr != null) {
            if (curr.data < key) {
                pre = curr;
                curr = curr.right;
            } else {
                curr = curr.left;
            }
        }
        curr = root;
        while (curr != null) {
            if (curr.data > key) {
                suc = curr;
                curr = curr.left;
            } else {
                curr = curr.right;
            }
        }
        ArrayList<Node> res = new ArrayList<>();
        res.add(pre);
        res.add(suc);
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def findPreSuc(self, root, key):
        pre = suc = None
        curr = root
        while curr:
            if curr.data < key:
                pre = curr
                curr = curr.right
            else:
                curr = curr.left
        curr = root
        while curr:
            if curr.data > key:
                suc = curr
                curr = curr.left
            else:
                curr = curr.right
        return [pre, suc]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
