--- ❤️ ---

# 🚀 _Day 230. Max Sum Path in Binary Tree_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/max-sum-path-in-binary-tree/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <climits>
#include <algorithm>

using namespace std;

struct TreeNode {
    int val;
    TreeNode *left;
    TreeNode *right;
    TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
};

class Solution {
public:
    int maxPathSum(TreeNode* root) {
        int max_sum = INT_MIN;
        helper(root, max_sum);
        return max_sum;
    }
    
    int helper(TreeNode* node, int& max_sum) {
        if (!node) return 0;
        
        int left_max = max(helper(node->left, max_sum), 0);
        int right_max = max(helper(node->right, max_sum), 0);
        
        int current_max = node->val + left_max + right_max;
        max_sum = max(max_sum, current_max);
        
        return node->val + max(left_max, right_max);
    }
};
```

## Code (Java)

```java
class TreeNode {
    int val;
    TreeNode left;
    TreeNode right;
    TreeNode(int x) { val = x; }
}

public class Solution {
    private int maxSum = Integer.MIN_VALUE;
    
    public int maxPathSum(TreeNode root) {
        helper(root);
        return maxSum;
    }
    
    private int helper(TreeNode node) {
        if (node == null) return 0;
        
        int leftMax = Math.max(helper(node.left), 0);
        int rightMax = Math.max(helper(node.right), 0);
        
        int currentMax = node.val + leftMax + rightMax;
        maxSum = Math.max(maxSum, currentMax);
        
        return node.val + Math.max(leftMax, rightMax);
    }
}
```

## Code (Python)

```python
class TreeNode:
    def __init__(self, x):
        self.val = x
        self.left = None
        self.right = None

class Solution:
    def maxPathSum(self, A):
        self.max_sum = float('-inf')
        self.helper(A)
        return self.max_sum
    
    def helper(self, node):
        if not node:
            return 0
        
        # Recursively get the maximum path sums from left and right subtrees
        left_max = max(self.helper(node.left), 0)
        right_max = max(self.helper(node.right), 0)
        
        # The maximum path sum where the current node is the root of the path
        current_max = node.val + left_max + right_max
        self.max_sum = max(self.max_sum, current_max)
        
        # Return the maximum path sum that can be extended from the current node
        return node.val + max(left_max, right_max)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
