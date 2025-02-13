---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Tree
  - Binary Search Tree
---

# 🚀 _Day 44. Pair Sum in BST_ 🧠

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/tree-gfg-160/problem/find-a-pair-with-given-target-in-bst)  

## 💡 **Problem Description:**

Given a **Binary Search Tree (BST)** and a target value, check whether there exists a **pair of nodes** in the BST whose sum equals the given target.  


## Code(C++)
```cpp
class Solution {
public:
    bool findTarget(Node* root, int target) {
        vector<int> inorder;
        function<void(Node*)> traverse = [&](Node* node) {
            if (!node) return;
            traverse(node->left);
            inorder.push_back(node->data);
            traverse(node->right);
        };
        traverse(root);
        int left = 0, right = inorder.size() - 1;
        while (left < right) {
            int sum = inorder[left] + inorder[right];
            if (sum == target) return true;
            sum < target ? left++ : right--;
        }
        return false;
    }
};
```

## Code (Java)

```java
class Solution {
    public boolean findTarget(Node root, int target) {
        List<Integer> inorder = new ArrayList<>();
        inorderTraversal(root, inorder);
        int left = 0, right = inorder.size() - 1;
        while (left < right) {
            int sum = inorder.get(left) + inorder.get(right);
            if (sum == target) return true;
            if (sum < target) left++;
            else right--;
        }
        return false;
    }

    private void inorderTraversal(Node node, List<Integer> inorder) {
        if (node == null) return;
        inorderTraversal(node.left, inorder);
        inorder.add(node.data);
        inorderTraversal(node.right, inorder);
    }
}
```

## Code (Python)

```python
class Solution:
    def findTarget(self, root, target):
        inorder = []
        def inorderTraversal(node):
            if not node:
                return
            inorderTraversal(node.left)
            inorder.append(node.data)
            inorderTraversal(node.right)

        inorderTraversal(root)
        left, right = 0, len(inorder) - 1
        while left < right:
            total = inorder[left] + inorder[right]
            if total == target:
                return True
            if total < target:
                left += 1
            else:
                right -= 1
        return False
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
