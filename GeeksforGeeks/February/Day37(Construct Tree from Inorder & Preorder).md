---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Tree
---

# 🚀 _Day 37. Construct Tree from Inorder & Preorder_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/tree-gfg-160/problem/construct-tree-1)  

## 💡 **Problem Description:**

Given two arrays representing the inorder and preorder traversals of a binary tree, construct the tree and return the root node of the constructed tree.  
**Note:** The output is written in postorder traversal.  

## Code(C++)
```cpp
class Solution {
public:
    int i = 0;
    unordered_map<int, int> m;
    Node* buildTree(vector<int>& inorder, vector<int>& preorder) {
        for (int j = 0; j < inorder.size(); j++) m[inorder[j]] = j;
        function<Node*(int, int)> f = [&](int l, int r) -> Node* {
            if (l > r) return nullptr;
            Node* root = new Node(preorder[i++]);
            root->left = f(l, m[root->data] - 1);
            root->right = f(m[root->data] + 1, r);
            return root;
        };
        return f(0, inorder.size() - 1);
    }
};
```

## Code (Java)

```java
class Solution {
    public static Node buildTree(int[] inorder, int[] preorder) {
        HashMap<Integer, Integer> m = new HashMap<>();
        for (int i = 0; i < inorder.length; i++) m.put(inorder[i], i);
        int[] idx = new int[1];
        return build(0, inorder.length - 1, preorder, m, idx);
    }
    static Node build(int l, int r, int[] pre, HashMap<Integer, Integer> m, int[] idx) {
        if(l > r) return null;
        Node root = new Node(pre[idx[0]++]);
        root.left = build(l, m.get(root.data) - 1, pre, m, idx);
        root.right = build(m.get(root.data) + 1, r, pre, m, idx);
        return root;
    }
}
```

## Code (Python)

```python
class Solution:
    def buildTree(self, inorder, preorder):
        m = {v: i for i, v in enumerate(inorder)}
        self.i = 0
        def f(l, r):
            if l > r:
                return None
            root = Node(preorder[self.i])
            self.i += 1
            pos = m[root.data]
            root.left = f(l, pos - 1)
            root.right = f(pos + 1, r)
            return root
        return f(0, len(inorder) - 1)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
