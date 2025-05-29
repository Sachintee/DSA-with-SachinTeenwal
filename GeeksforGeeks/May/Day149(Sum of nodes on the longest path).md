# *149. Sum of nodes on the longest path*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/sum-of-the-longest-bloodline-of-a-tree/1)

## **🧩 Problem Description**

Given a binary tree, find the **sum of the nodes** on the **longest path** from the root to any leaf.

* If there are multiple root-to-leaf paths of the same maximum length, return the maximum sum among them.


## Code(C++)
```cpp
class Solution {
  public:
    pair<int, int> dfs(Node* root) {
        if (!root) return {0, 0};
        auto l = dfs(root->left), r = dfs(root->right);
        if (l.first > r.first) return {l.first + 1, l.second + root->data};
        if (r.first > l.first) return {r.first + 1, r.second + root->data};
        return {l.first + 1, max(l.second, r.second) + root->data};
    }
    int sumOfLongRootToLeafPath(Node* root) {
        return dfs(root).second;
    }
};
```

## Code (Java)

```java
class Solution {
    public int sumOfLongRootToLeafPath(Node root) {
        return dfs(root)[1];
    }

    int[] dfs(Node node) {
        if (node == null) return new int[]{0, 0};
        int[] l = dfs(node.left), r = dfs(node.right);
        if (l[0] > r[0]) return new int[]{l[0] + 1, l[1] + node.data};
        if (r[0] > l[0]) return new int[]{r[0] + 1, r[1] + node.data};
        return new int[]{l[0] + 1, Math.max(l[1], r[1]) + node.data};
    }
}
```

## Code (Python)

```python
class Solution:
    def sumOfLongRootToLeafPath(self, root):
        def dfs(node):
            if not node: return (0, 0)
            l = dfs(node.left)
            r = dfs(node.right)
            if l[0] > r[0]: return (l[0] + 1, l[1] + node.data)
            if r[0] > l[0]: return (r[0] + 1, r[1] + node.data)
            return (l[0] + 1, max(l[1], r[1]) + node.data)
        return dfs(root)[1]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
