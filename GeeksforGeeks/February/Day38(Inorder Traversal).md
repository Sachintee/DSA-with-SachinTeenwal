---
Difficulty: Easy  
Source: 160 Days of Problem Solving  
Tags:
  - Tree
---

# 🚀 _Day 38. Inorder Traversal_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/tree-gfg-160/problem/inorder-traversal)  

## 💡 **Problem Description:**

Given a Binary Tree, your task is to return its In-Order Traversal.

An inorder traversal first visits the left subtree (including its entire subtree), then visits the node, and finally visits the right subtree (including its entire subtree).

## Code(C++)
```cpp
class Solution {
public:
    void f(Node* r, vector<int>& a) {
        if (!r)
            return;
        f(r->left, a);
        a.push_back(r->data);
        f(r->right, a);
    }
    
    vector<int> inOrder(Node* r) {
        vector<int> a;
        f(r, a);
        return a;
    }
};
```

## Code (Java)

```java
class Solution {
    ArrayList<Integer> inOrder(Node r) {
        ArrayList<Integer> a = new ArrayList<>();
        f(r, a);
        return a;
    }
    void f(Node r, ArrayList<Integer> a) {
        if (r == null) return;
        f(r.left, a);
        a.add(r.data);
        f(r.right, a);
    }
}
```

## Code (Python)

```python
class Solution:
    def inOrder(self, root):
        a = []
        def f(r):
            if r:
                f(r.left)
                a.append(r.data)
                f(r.right)
        f(root)
        return a
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
