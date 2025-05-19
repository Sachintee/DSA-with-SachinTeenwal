--- ❤️ ---

# 🚀 _Day 139. Recover Binary Search Tree_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/recover-binary-search-tree/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <stack>
#include <algorithm>

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
    vector<int> recoverTree(TreeNode* A) {
        TreeNode *prev = nullptr, *first = nullptr, *second = nullptr;
        stack<TreeNode*> st;
        TreeNode* current = A;
        
        while (true) {
            if (current != nullptr) {
                st.push(current);
                current = current->left;
            } else if (!st.empty()) {
                current = st.top();
                st.pop();
                if (prev != nullptr && prev->val > current->val) {
                    if (first == nullptr) {
                        first = prev;
                    }
                    second = current;
                }
                prev = current;
                current = current->right;
            } else {
                break;
            }
        }
        
        vector<int> result;
        result.push_back(first->val);
        result.push_back(second->val);
        sort(result.begin(), result.end());
        return result;
    }
};
```

## Code (Java)

```java
import java.util.*;

// Definition for a binary tree node.
class TreeNode {
    int val;
    TreeNode left;
    TreeNode right;
    TreeNode(int x) { val = x; }
}

public class Solution {
    public ArrayList<Integer> recoverTree(TreeNode A) {
        TreeNode prev = null, first = null, second = null;
        Stack<TreeNode> stack = new Stack<>();
        TreeNode current = A;
        
        while (true) {
            if (current != null) {
                stack.push(current);
                current = current.left;
            } else if (!stack.isEmpty()) {
                current = stack.pop();
                if (prev != null && prev.val > current.val) {
                    if (first == null) {
                        first = prev;
                    }
                    second = current;
                }
                prev = current;
                current = current.right;
            } else {
                break;
            }
        }
        
        ArrayList<Integer> result = new ArrayList<>();
        result.add(first.val);
        result.add(second.val);
        Collections.sort(result);
        return result;
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
    # @return a list of integers
    def recoverTree(self, A):
        prev = None
        first = None
        second = None
        
        current = A
        stack = []
        
        while True:
            if current is not None:
                stack.append(current)
                current = current.left
            elif stack:
                current = stack.pop()
                if prev is not None and prev.val > current.val:
                    if first is None:
                        first = prev
                    second = current
                prev = current
                current = current.right
            else:
                break
        
        return sorted([first.val, second.val])
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
