# *126. Left View of Binary Tree*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/left-view-of-binary-tree/1)


## **🧩 Problem Description**

You are given the root of a binary tree. Your task is to return the **left view** of the binary tree.
The left view is defined as the set of nodes visible when the tree is observed from the **left side**.

If the tree is empty, return an empty list.

## Code(C++)
```cpp
class Solution {
  public:
    vector<int> leftView(Node *root) {
        if (!root) return {};
        vector<int> res;
        queue<Node*> q;
        q.push(root);
        while (!q.empty()) {
            int n = q.size();
            for (int i = 0; i < n; i++) {
                Node* cur = q.front(); q.pop();
                if (i == 0) res.push_back(cur->data);
                if (cur->left) q.push(cur->left);
                if (cur->right) q.push(cur->right);
            }
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    ArrayList<Integer> leftView(Node root) {
        if (root == null) return new ArrayList<>();
        ArrayList<Integer> res = new ArrayList<>();
        Queue<Node> q = new LinkedList<>();
        q.add(root);
        while (!q.isEmpty()) {
            int n = q.size();
            for (int i = 0; i < n; i++) {
                Node cur = q.poll();
                if (i == 0) res.add(cur.data);
                if (cur.left != null) q.add(cur.left);
                if (cur.right != null) q.add(cur.right);
            }
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def LeftView(self, root):
        if not root: return []
        res, q = [], [root]
        while q:
            res.append(q[0].data)
            q = [child for node in q for child in (node.left, node.right) if child]
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
