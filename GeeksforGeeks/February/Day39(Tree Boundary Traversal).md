---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Tree
---

# 🚀 _Day 39. Tree Boundary Traversal_ 🧠

The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/tree-gfg-160/problem/boundary-traversal-of-binary-tree)

## 💡 **Problem Description:**

Given a binary tree, the task is to return a list of nodes representing its boundary traversal in an **anticlockwise direction**, starting from the **root**. The boundary includes:
1. The **left boundary** (excluding the leaf nodes).
2. All the **leaf nodes** (both from left and right subtrees).
3. The **right boundary** (excluding the leaf nodes), added in **reverse order**.


## Code(C++)
```cpp
class Solution {
    void lb(Node* r, vector<int>& v) {
        if (!r || (!r->left && !r->right)) return;
        v.push_back(r->data);
        lb(r->left ? r->left : r->right, v);
    }
    void rb(Node* r, vector<int>& v) {
        if (!r || (!r->left && !r->right)) return;
        rb(r->right ? r->right : r->left, v);
        v.push_back(r->data);
    }
    void leaf(Node* r, vector<int>& v) {
        if (!r) return;
        leaf(r->left, v);
        if (!r->left && !r->right) v.push_back(r->data);
        leaf(r->right, v);
    }
public:
    vector<int> boundaryTraversal(Node* r) {
        if (!r) return {};
        vector<int> v = {r->data};
        lb(r->left, v);
        leaf(r->left, v);
        leaf(r->right, v);
        rb(r->right, v);
        return v;
    }
};
```

## Code (Java)

```java
class Solution {
    void lb(Node r, ArrayList<Integer> v) {
        if(r==null || (r.left==null && r.right==null)) return;
        v.add(r.data);
        lb(r.left!=null ? r.left : r.right, v);
    }
    void rb(Node r, ArrayList<Integer> v) {
        if(r==null || (r.left==null && r.right==null)) return;
        rb(r.right!=null ? r.right : r.left, v);
        v.add(r.data);
    }
    void leaf(Node r, ArrayList<Integer> v) {
        if(r==null)return;
        leaf(r.left,v);
        if(r.left==null && r.right==null) v.add(r.data);
        leaf(r.right,v);
    }
    public ArrayList<Integer> boundaryTraversal(Node r) {
        ArrayList<Integer> v = new ArrayList<>();
        if(r==null)return v;
        v.add(r.data);
        lb(r.left, v);
        leaf(r.left, v);
        leaf(r.right, v);
        rb(r.right, v);
        return v;
    }
}
```

## Code (Python)

```python
class Solution:
    def boundaryTraversal(self, root):
        if not root:
            return []
        res = [root.data] if root.left or root.right else []

        cur = root.left
        while cur:
            if cur.left or cur.right:
                res.append(cur.data)
            cur = cur.left if cur.left else cur.right

        def leaf_nodes(node):
            if not node:
                return
            leaf_nodes(node.left)
            if not node.left and not node.right:
                res.append(node.data)
            leaf_nodes(node.right)

        leaf_nodes(root)

        right_boundary = []
        cur = root.right
        while cur:
            if cur.left or cur.right:
                right_boundary.append(cur.data)
            cur = cur.right if cur.right else cur.left

        res += reversed(right_boundary)
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
