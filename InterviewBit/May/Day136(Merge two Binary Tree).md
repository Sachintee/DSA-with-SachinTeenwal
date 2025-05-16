--- ❤️ ---

# 🚀 _Day 136. Merge two Binary Tree_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/merge-two-binary-tree/)

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
    TreeNode* solve(TreeNode* A, TreeNode* B) {
        if (!A && !B) return NULL;
        if (!A) return B;
        if (!B) return A;
        // Create a new node with the sum of A and B's values
        TreeNode* new_node = new TreeNode(A->val + B->val);
        // Recursively merge the left and right subtrees
        new_node->left = solve(A->left, B->left);
        new_node->right = solve(A->right, B->right);
        return new_node;
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
    public TreeNode solve(TreeNode A, TreeNode B) {
        if (A == null && B == null) return null;
        if (A == null) return B;
        if (B == null) return A;
        // Create a new node with the sum of A and B's values
        TreeNode newNode = new TreeNode(A.val + B.val);
        // Recursively merge the left and right subtrees
        newNode.left = solve(A.left, B.left);
        newNode.right = solve(A.right, B.right);
        return newNode;
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
    # @param B : root node of tree
    # @return the root node in the tree
    def solve(self, A, B):
        if not A and not B:
            return None
        if not A:
            return B
        if not B:
            return A
        # Create a new node with the sum of A and B's values
        new_node = TreeNode(A.val + B.val)
        # Recursively merge the left and right subtrees
        new_node.left = self.solve(A.left, B.left)
        new_node.right = self.solve(A.right, B.right)
        return new_node
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
