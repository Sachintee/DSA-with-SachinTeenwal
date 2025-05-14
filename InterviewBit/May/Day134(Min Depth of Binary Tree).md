--- ❤️ ---

# 🚀 _Day 134. Min Depth of Binary Tree_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/min-depth-of-binary-tree/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <queue>
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
    int minDepth(TreeNode* A) {
        if (!A) return 0;
        queue<pair<TreeNode*, int>> q;
        q.push({A, 1});
        while (!q.empty()) {
            TreeNode* node = q.front().first;
            int depth = q.front().second;
            q.pop();
            if (!node->left && !node->right) {
                return depth;
            }
            if (node->left) {
                q.push({node->left, depth + 1});
            }
            if (node->right) {
                q.push({node->right, depth + 1});
            }
        }
        return 0;
    }
};
```

## Code (Java)

```java
import java.util.LinkedList;
import java.util.Queue;

// Definition for a binary tree node.
class TreeNode {
    int val;
    TreeNode left;
    TreeNode right;
    TreeNode(int x) { val = x; }
}

public class Solution {
    public int minDepth(TreeNode A) {
        if (A == null) return 0;
        Queue<Pair<TreeNode, Integer>> queue = new LinkedList<>();
        queue.add(new Pair<>(A, 1));
        while (!queue.isEmpty()) {
            Pair<TreeNode, Integer> current = queue.poll();
            TreeNode node = current.getKey();
            int depth = current.getValue();
            if (node.left == null && node.right == null) {
                return depth;
            }
            if (node.left != null) {
                queue.add(new Pair<>(node.left, depth + 1));
            }
            if (node.right != null) {
                queue.add(new Pair<>(node.right, depth + 1));
            }
        }
        return 0;
    }

    static class Pair<K, V> {
        private K key;
        private V value;
        public Pair(K key, V value) {
            this.key = key;
            this.value = value;
        }
        public K getKey() { return key; }
        public V getValue() { return value; }
    }
}
```

## Code (Python)

```python
from collections import deque

# Definition for a binary tree node.
class TreeNode:
    def __init__(self, x):
        self.val = x
        self.left = None
        self.right = None

class Solution:
    # @param A : root node of tree
    # @return an integer
    def minDepth(self, A):
        if not A:
            return 0
        queue = deque()
        queue.append((A, 1))
        while queue:
            node, depth = queue.popleft()
            if not node.left and not node.right:
                return depth
            if node.left:
                queue.append((node.left, depth + 1))
            if node.right:
                queue.append((node.right, depth + 1))
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
