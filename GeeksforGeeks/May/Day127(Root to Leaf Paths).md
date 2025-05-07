# *127. Root to Leaf Paths*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/root-to-leaf-paths/1)

## **🧩 Problem Description**

Given a binary tree, find all the possible paths from the root node to all the leaf nodes.  
A leaf node is a node that does not have any children. The paths should be returned in such a way that the paths from the left subtree of any node are listed first, followed by paths from the right subtree.


## Code(C++)
```cpp
class Solution {
  public:
    vector<vector<int>> Paths(Node* root) {
        vector<vector<int>> res, path;
        vector<int> curr;
        function<void(Node*)> dfs = [&](Node* n) {
            if (!n) return;
            curr.push_back(n->data);
            if (!n->left && !n->right) res.push_back(curr);
            else dfs(n->left), dfs(n->right);
            curr.pop_back();
        };
        dfs(root);
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public static ArrayList<ArrayList<Integer>> Paths(Node r) {
        var res = new ArrayList<ArrayList<Integer>>();
        var curr = new ArrayList<Integer>();
        dfs(r, res, curr);
        return res;
    }
    static void dfs(Node n, ArrayList<ArrayList<Integer>> res, ArrayList<Integer> curr) {
        if (n == null) return;
        curr.add(n.data);
        if (n.left == null && n.right == null) res.add(new ArrayList<>(curr));
        else {
            dfs(n.left, res, curr);
            dfs(n.right, res, curr);
        }
        curr.remove(curr.size() - 1);
    }
}
```

## Code (Python)

```python
class Solution:
    def Paths(self, root):
        res, curr = [], []
        def dfs(n):
            if not n: return
            curr.append(n.data)
            if not n.left and not n.right:
                res.append(curr.copy())
            else:
                dfs(n.left); dfs(n.right)
            curr.pop()
        dfs(root)
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
