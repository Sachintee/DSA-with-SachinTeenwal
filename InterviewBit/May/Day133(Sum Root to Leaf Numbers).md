--- ❤️ ---

# 🚀 _Day 133. Sum Root to Leaf Numbers_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/sum-root-to-leaf-numbers/)

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
    int sumNumbers(TreeNode* A) {
        return dfs(A, 0);
    }
    
    int dfs(TreeNode* node, int currentSum) {
        if (!node) return 0;
        currentSum = (currentSum * 10 + node->val) % 1003;
        if (!node->left && !node->right) {
            return currentSum;
        }
        return (dfs(node->left, currentSum) + dfs(node->right, currentSum)) % 1003;
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
    public int sumNumbers(TreeNode A) {
        return dfs(A, 0);
    }
    
    private int dfs(TreeNode node, int currentSum) {
        if (node == null) return 0;
        currentSum = (currentSum * 10 + node.val) % 1003;
        if (node.left == null && node.right == null) {
            return currentSum;
        }
        return (dfs(node.left, currentSum) + dfs(node.right, currentSum)) % 1003;
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
    def sumNumbers(self, A):
        def dfs(node, current_sum):
            if not node:
                return 0
            current_sum = (current_sum * 10 + node.val) % 1003
            if not node.left and not node.right:
                return current_sum
            return (dfs(node.left, current_sum) + dfs(node.right, current_sum)) % 1003
        
        return dfs(A, 0)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
