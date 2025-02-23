--- ❤️ ---

# 🚀 _Day 54. Construct Binary Tree from Preorder and Postorder Traversal_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/construct-binary-tree-from-preorder-and-postorder-traversal/submissions/1552947184/?envType=daily-question&envId=2025-02-23)

## 🎯 **My Approach:**


## Code(C++)
```cpp
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
 * };
 */
class Solution {
public:
    TreeNode* constructFromPrePost(vector<int>& preorder, vector<int>& postorder) {
        unordered_map<int, int> pos;
        int n = postorder.size();
        for (int i = 0; i < n; ++i) {
            pos[postorder[i]] = i;
        }
        function<TreeNode*(int, int, int, int)> dfs = [&](int a, int b, int c, int d) -> TreeNode* {
            if (a > b) {
                return nullptr;
            }
            TreeNode* root = new TreeNode(preorder[a]);
            if (a == b) {
                return root;
            }
            int i = pos[preorder[a + 1]];
            int m = i - c + 1;
            root->left = dfs(a + 1, a + m, c, i);
            root->right = dfs(a + m + 1, b, i + 1, d - 1);
            return root;
        };
        return dfs(0, n - 1, 0, n - 1);
    }
};
```

## Code (Java)

```java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode() {}
 *     TreeNode(int val) { this.val = val; }
 *     TreeNode(int val, TreeNode left, TreeNode right) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */
class Solution {
    private Map<Integer, Integer> pos = new HashMap<>();
    private int[] preorder;

    public TreeNode constructFromPrePost(int[] preorder, int[] postorder) {
        this.preorder = preorder;
        for (int i = 0; i < postorder.length; ++i) {
            pos.put(postorder[i], i);
        }
        return dfs(0, preorder.length - 1, 0, postorder.length - 1);
    }

    private TreeNode dfs(int a, int b, int c, int d) {
        if (a > b) {
            return null;
        }
        TreeNode root = new TreeNode(preorder[a]);
        if (a == b) {
            return root;
        }
        int i = pos.get(preorder[a + 1]);
        int m = i - c + 1;
        root.left = dfs(a + 1, a + m, c, i);
        root.right = dfs(a + m + 1, b, i + 1, d - 1);
        return root;
    }
}
```

## Code (Python)

```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def constructFromPrePost(
        self, preorder: List[int], postorder: List[int]
    ) -> Optional[TreeNode]:
        def dfs(a: int, b: int, c: int, d: int) -> Optional[TreeNode]:
            if a > b:
                return None
            root = TreeNode(preorder[a])
            if a == b:
                return root
            i = pos[preorder[a + 1]]
            m = i - c + 1
            root.left = dfs(a + 1, a + m, c, i)
            root.right = dfs(a + m + 1, b, i + 1, d - 1)
            return root

        pos = {x: i for i, x in enumerate(postorder)}
        return dfs(0, len(preorder) - 1, 0, len(postorder) - 1)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
