# *116. Is Binary Tree Heap*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/is-binary-tree-heap/1)


## **🧩 Problem Description**

Given a binary tree, determine whether it satisfies the properties of a **Max-Heap**.

A binary tree is a **Max-Heap** if:

1. **Completeness**: All levels of the tree are completely filled except possibly the last, which is filled from left to right.
2. **Heap Property**: The value of every node is **greater than or equal to** the values of its children.



## Code(C++)
```cpp
class Solution {
    int c(Node* r) { return r ? 1 + c(r->left) + c(r->right) : 0; }
    bool p(Node* r, int i, int n) {
        return !r
            || (i < n
                && (!r->left  || r->data >= r->left->data)
                && (!r->right || r->data >= r->right->data)
                && p(r->left,  2*i+1, n)
                && p(r->right, 2*i+2, n)
              );
    }
  public:
    bool isHeap(Node* tree) {
        return p(tree, 0, c(tree));
    }
};
```

## Code (Java)

```java
class Solution {
    int c(Node r){return r==null?0:1+c(r.left)+c(r.right);}
    boolean p(Node r,int i,int n){
        return r==null
            || (i<n
                && (r.left  ==null || r.data>=r.left.data)
                && (r.right ==null || r.data>=r.right.data)
                &&  p(r.left,  2*i+1, n)
                &&  p(r.right, 2*i+2, n)
               );
    }
    boolean isHeap(Node tree){
        return p(tree,0,c(tree));
    }
}
```

## Code (Python)

```python
class Solution:
    def c(self, r):
        return 1 + self.c(r.left) + self.c(r.right) if r else 0
    def p(self, r, i, n):
        return (not r) or (
            i < n
            and (not r.left  or r.data >= r.left.data)
            and (not r.right or r.data >= r.right.data)
            and self.p(r.left,  2*i+1, n)
            and self.p(r.right, 2*i+2, n)
        )
    def isHeap(self, root):
        return self.p(root, 0, self.c(root))
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
