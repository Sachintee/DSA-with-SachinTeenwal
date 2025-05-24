--- ❤️ ---

# 🚀 _Day 144. Construct BST from Preorder_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/construct-bst-from-preorder/)

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
int n, idx = 0;
vector<int> pre;
TreeNode* helper(int lower, int upper) {
    if (idx == n) 
        return NULL;
    int val = pre[idx];
    if (val < lower || val > upper) 
        return NULL;
    idx++;
    TreeNode* root = new TreeNode(val);
    root->left = helper(lower, val);
    root->right = helper(val, upper);
    return root;
}
TreeNode* Solution::constructBST(vector<int> &A) {
    pre = A;
    n = A.size();
    idx = 0;
    return helper(-2000000000, 2000000000);
}

```

## Code (Java)

```java
/**
 * Definition for binary tree
 * class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int x) {
 *      val = x;
 *      left=null;
 *      right=null;
 *     }
 * }
 */
class Solution{
    int n, idx = 0;
    int[] pre;
    public TreeNode helper(int lower, int upper) {
        if (idx == n) 
            return null;
        int val = pre[idx];
        if (val < lower || val > upper) 
            return null;
        idx++;
        TreeNode root = new TreeNode(val);
        root.left = helper(lower, val);
        root.right = helper(val, upper);
        return root;
    }
    public TreeNode constructBST(int[] A){
        pre = A;
        n = A.length;
        return helper(Integer.MIN_VALUE, Integer.MAX_VALUE);
    }
}


```

## Code (Python)

```python
# Definition for a  binary tree node
# class TreeNode:
#    def __init__(self, x):
#        self.val = x
#        self.left = None
#        self.right = None
sys.setrecursionlimit(200000)

class Solution:
    def constructBST(self, A):
        def helper(lower = float('-inf'), upper = float('inf')):
            nonlocal idx
            if idx == n:
                return None
            val = A[idx]
            if val < lower or val > upper:
                return None
            idx += 1
            root = TreeNode(val)
            root.left = helper(lower, val)
            root.right = helper(val, upper)
            return root
        
        idx = 0
        n = len(A)
        return helper()
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
