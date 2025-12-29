

# 🚀 _Day 363. Valid Binary Search Tree_ 


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/valid-binary-search-tree/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
/**
 * Definition for binary tree
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode(int x) : val(x), left(NULL), right(NULL) {}
 * };
 */
class Solution {
public:
    bool check(TreeNode* node, long long low, long long high) {
        if (!node) return true;

        if (node->val <= low || node->val >= high)
            return false;

        return check(node->left, low, node->val) &&
               check(node->right, node->val, high);
    }

    int isValidBST(TreeNode* A) {
        return check(A, LLONG_MIN, LLONG_MAX) ? 1 : 0;
    }
};

```

## Code (Java)

```java
/**
 * Definition for binary tree
 * class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int x) { val = x; }
 * }
 */
public class Solution {
    private boolean check(TreeNode node, long low, long high) {
        if (node == null) return true;

        if (node.val <= low || node.val >= high)
            return false;

        return check(node.left, low, node.val) &&
               check(node.right, node.val, high);
    }

    public int isValidBST(TreeNode A) {
        return check(A, Long.MIN_VALUE, Long.MAX_VALUE) ? 1 : 0;
    }
}

```

## Code (Python3)

```python
class Solution:
    def isValidBST(self, A):
        def check(node, low, high):
            if not node:
                return True

            # BST condition
            if node.val <= low or node.val >= high:
                return False

            # Check left and right subtrees
            return (check(node.left, low, node.val) and
                    check(node.right, node.val, high))

        return 1 if check(A, float('-inf'), float('inf')) else 0

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
