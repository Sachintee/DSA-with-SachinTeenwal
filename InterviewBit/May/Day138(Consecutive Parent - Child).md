--- ❤️ ---

# 🚀 _Day 138. Consecutive Parent - Child_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/consecutive-parent-child/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <cstdlib> // for abs function

// Definition for a binary tree node.
struct TreeNode {
    int val;
    TreeNode *left;
    TreeNode *right;
    TreeNode(int x) : val(x), left(NULL), right(NULL) {}
};

class Solution {
public:
    int consecutiveNodes(TreeNode* A) {
        if (!A) return 0;
        int count = 0;
        // Check left child
        if (A->left) {
            if (abs(A->val - A->left->val) == 1) {
                count++;
            }
            count += consecutiveNodes(A->left);
        }
        // Check right child
        if (A->right) {
            if (abs(A->val - A->right->val) == 1) {
                count++;
            }
            count += consecutiveNodes(A->right);
        }
        return count;
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
    public int consecutiveNodes(TreeNode A) {
        if (A == null) return 0;
        int count = 0;
        // Check left child
        if (A.left != null) {
            if (Math.abs(A.val - A.left.val) == 1) {
                count++;
            }
            count += consecutiveNodes(A.left);
        }
        // Check right child
        if (A.right != null) {
            if (Math.abs(A.val - A.right.val) == 1) {
                count++;
            }
            count += consecutiveNodes(A.right);
        }
        return count;
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
    def consecutiveNodes(self, A):
        if not A:
            return 0
        count = 0
        # Check left child
        if A.left:
            if abs(A.val - A.left.val) == 1:
                count += 1
            count += self.consecutiveNodes(A.left)
        # Check right child
        if A.right:
            if abs(A.val - A.right.val) == 1:
                count += 1
            count += self.consecutiveNodes(A.right)
        return count
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
