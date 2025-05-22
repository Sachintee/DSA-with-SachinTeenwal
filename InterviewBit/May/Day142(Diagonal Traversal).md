--- ❤️ ---

# 🚀 _Day 142. Diagonal Traversal_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/diagonal-traversal/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <map>
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
    vector<int> solve(TreeNode* A) {
        vector<int> result;
        if (!A) return result;
        
        map<int, vector<int>> diagonalMap;
        traverse(A, 0, diagonalMap);
        
        for (auto& entry : diagonalMap) {
            result.insert(result.end(), entry.second.begin(), entry.second.end());
        }
        
        return result;
    }
    
    void traverse(TreeNode* node, int level, map<int, vector<int>>& diagonalMap) {
        if (!node) return;
        diagonalMap[level].push_back(node->val);
        traverse(node->left, level + 1, diagonalMap);
        traverse(node->right, level, diagonalMap);
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
    public ArrayList<Integer> solve(TreeNode A) {
        ArrayList<Integer> result = new ArrayList<>();
        if (A == null) return result;
        
        TreeMap<Integer, ArrayList<Integer>> diagonalMap = new TreeMap<>();
        traverse(A, 0, diagonalMap);
        
        for (ArrayList<Integer> list : diagonalMap.values()) {
            result.addAll(list);
        }
        
        return result;
    }
    
    private void traverse(TreeNode node, int level, TreeMap<Integer, ArrayList<Integer>> diagonalMap) {
        if (node == null) return;
        diagonalMap.putIfAbsent(level, new ArrayList<>());
        diagonalMap.get(level).add(node.val);
        traverse(node.left, level + 1, diagonalMap);
        traverse(node.right, level, diagonalMap);
    }
}
```

## Code (Python)

```python
from collections import defaultdict

# Definition for a binary tree node.
class TreeNode:
    def __init__(self, x):
        self.val = x
        self.left = None
        self.right = None

class Solution:
    # @param A : root node of tree
    # @return a list of integers
    def solve(self, A):
        if not A:
            return []
        
        diagonal_map = defaultdict(list)
        
        def traverse(node, level):
            if not node:
                return
            diagonal_map[level].append(node.val)
            traverse(node.left, level + 1)
            traverse(node.right, level)
        
        traverse(A, 0)
        
        result = []
        for level in sorted(diagonal_map.keys()):
            result.extend(diagonal_map[level])
        
        return result
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
