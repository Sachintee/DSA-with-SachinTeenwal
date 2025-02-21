--- ❤️ ---

# 🚀 _Day 52. Find Elements in a Contaminated Binary Tree_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/find-elements-in-a-contaminated-binary-tree/description/?envType=daily-question&envId=2025-02-21)

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
class FindElements {
public:
    FindElements(TreeNode* root) {
        root->val = 0;
        dfs(root);
    }

    bool find(int target) {
        return s.contains(target);
    }

private:
    unordered_set<int> s;

    void dfs(TreeNode* root) {
        s.insert(root->val);
        if (root->left) {
            root->left->val = root->val * 2 + 1;
            dfs(root->left);
        }
        if (root->right) {
            root->right->val = root->val * 2 + 2;
            dfs(root->right);
        }
    };
};

/**
 * Your FindElements object will be instantiated and called as such:
 * FindElements* obj = new FindElements(root);
 * bool param_1 = obj->find(target);
 */
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
class FindElements {
    private Set<Integer> s = new HashSet<>();

    public FindElements(TreeNode root) {
        root.val = 0;
        dfs(root);
    }

    public boolean find(int target) {
        return s.contains(target);
    }

    private void dfs(TreeNode root) {
        s.add(root.val);
        if (root.left != null) {
            root.left.val = root.val * 2 + 1;
            dfs(root.left);
        }
        if (root.right != null) {
            root.right.val = root.val * 2 + 2;
            dfs(root.right);
        }
    }
}

/**
 * Your FindElements object will be instantiated and called as such:
 * FindElements obj = new FindElements(root);
 * boolean param_1 = obj.find(target);
 */
```

## Code (Python)

```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class FindElements:

    def __init__(self, root: Optional[TreeNode]):
        def dfs(root: Optional[TreeNode]):
            self.s.add(root.val)
            if root.left:
                root.left.val = root.val * 2 + 1
                dfs(root.left)
            if root.right:
                root.right.val = root.val * 2 + 2
                dfs(root.right)

        root.val = 0
        self.s = set()
        dfs(root)

    def find(self, target: int) -> bool:
        return target in self.s


# Your FindElements object will be instantiated and called as such:
# obj = FindElements(root)
# param_1 = obj.find(target)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
