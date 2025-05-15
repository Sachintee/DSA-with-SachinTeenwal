--- ❤️ ---

# 🚀 _Day 135. Remove Half Nodes_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/remove-half-nodes/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
using namespace std;

// Definition for a binary tree node.
struct TreeNode {
    int val;
    TreeNode *left;
    TreeNode *right;
    TreeNode(int x) : val(x), left(NULL), right(NULL) {}
};

class Solution {
public:
    TreeNode* solve(TreeNode* A) {
        if (!A) return NULL;
        // Process left and right subtrees first
        A->left = solve(A->left);
        A->right = solve(A->right);
        // If current node has only one child, return that child
        if (A->left == NULL && A->right != NULL)
            return A->right;
        if (A->right == NULL && A->left != NULL)
            return A->left;
        // If both children are present or both are absent, return the node as is
        return A;
    }
};
```

## Code (Java)

```java
// Definition for a binary tree node.
class TreeNode {
    int val;
    TreeNode left;
    TreeNode right;
    TreeNode(int x) { val = x; }
}

public class Solution {
    public TreeNode solve(TreeNode A) {
        if (A == null) return null;
        // Process left and right subtrees first
        A.left = solve(A.left);
        A.right = solve(A.right);
        // If current node has only one child, return that child
        if (A.left == null && A.right != null)
            return A.right;
        if (A.right == null && A.left != null)
            return A.left;
        // If both children are present or both are absent, return the node as is
        return A;
    }
}
```

## Code (Python)

```python
# Definition for a binary tree node.
class TreeNode:
    def __init__(self, x):
        self.val = x
        self.left = None
        self.right = None

class Solution:
    # @param A : root node of tree
    # @return the root node in the tree
    def solve(self, A):
        if not A:
            return None
        # Process left and right subtrees first
        A.left = self.solve(A.left)
        A.right = self.solve(A.right)
        # If current node has only one child, return that child
        if A.left is None and A.right is not None:
            return A.right
        if A.right is None and A.left is not None:
            return A.left
        # If both children are present or both are absent, return the node as is
        return A
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
