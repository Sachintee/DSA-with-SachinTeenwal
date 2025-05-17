--- ❤️ ---

# 🚀 _Day 137. Symmetric Binary Tree_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/symmetric-binary-tree/)

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
    int isSymmetric(TreeNode* A) {
        if (!A) return 1;
        return isMirror(A->left, A->right) ? 1 : 0;
    }
    
    bool isMirror(TreeNode* left, TreeNode* right) {
        if (!left && !right) return true;
        if (!left || !right) return false;
        return (left->val == right->val) && isMirror(left->left, right->right) && isMirror(left->right, right->left);
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
    public int isSymmetric(TreeNode A) {
        if (A == null) return 1;
        return isMirror(A.left, A.right) ? 1 : 0;
    }
    
    private boolean isMirror(TreeNode left, TreeNode right) {
        if (left == null && right == null) return true;
        if (left == null || right == null) return false;
        return (left.val == right.val) && isMirror(left.left, right.right) && isMirror(left.right, right.left);
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
    # @return an integer
    def isSymmetric(self, A):
        if not A:
            return 1
        return 1 if self.isMirror(A.left, A.right) else 0
    
    def isMirror(self, left, right):
        if not left and not right:
            return True
        if not left or not right:
            return False
        return (left.val == right.val) and self.isMirror(left.left, right.right) and self.isMirror(left.right, right.left)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
