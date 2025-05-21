--- ❤️ ---

# 🚀 _Day 141. Vertical Sum of a Binary Tree_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/vertical-sum-of-a-binary-tree/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <queue>
#include <map>
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
    vector<int> verticalSum(TreeNode* A) {
        vector<int> result;
        if (!A) return result;
        
        map<int, int> columnSums;
        queue<pair<TreeNode*, int>> q;
        q.push({A, 0});
        
        while (!q.empty()) {
            auto current = q.front();
            q.pop();
            TreeNode* node = current.first;
            int col = current.second;
            columnSums[col] += node->val;
            
            if (node->left) {
                q.push({node->left, col - 1});
            }
            if (node->right) {
                q.push({node->right, col + 1});
            }
        }
        
        for (auto& entry : columnSums) {
            result.push_back(entry.second);
        }
        
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
    public ArrayList<Integer> verticalSum(TreeNode A) {
        ArrayList<Integer> result = new ArrayList<>();
        if (A == null) return result;
        
        TreeMap<Integer, Integer> columnSums = new TreeMap<>();
        Queue<Pair<TreeNode, Integer>> queue = new LinkedList<>();
        queue.offer(new Pair<>(A, 0));
        
        while (!queue.isEmpty()) {
            Pair<TreeNode, Integer> current = queue.poll();
            TreeNode node = current.getKey();
            int col = current.getValue();
            
            columnSums.put(col, columnSums.getOrDefault(col, 0) + node.val);
            
            if (node.left != null) {
                queue.offer(new Pair<>(node.left, col - 1));
            }
            if (node.right != null) {
                queue.offer(new Pair<>(node.right, col + 1));
            }
        }
        
        for (int sum : columnSums.values()) {
            result.add(sum);
        }
        
        return result;
    }
    
    static class Pair<K, V> {
        private K key;
        private V value;
        
        public Pair(K key, V value) {
            this.key = key;
            this.value = value;
        }
        
        public K getKey() {
            return key;
        }
        
        public V getValue() {
            return value;
        }
    }
}
```

## Code (Python)

```python
from collections import deque, defaultdict

# Definition for a binary tree node.
class TreeNode:
    def __init__(self, x):
        self.val = x
        self.left = None
        self.right = None

class Solution:
    # @param A : root node of tree
    # @return a list of integers
    def verticalSum(self, A):
        if not A:
            return []
        
        column_sums = defaultdict(int)
        min_col = max_col = 0
        queue = deque([(A, 0)])
        
        while queue:
            node, col = queue.popleft()
            column_sums[col] += node.val
            min_col = min(min_col, col)
            max_col = max(max_col, col)
            
            if node.left:
                queue.append((node.left, col - 1))
            if node.right:
                queue.append((node.right, col + 1))
        
        # Prepare the result by iterating from min_col to max_col
        result = []
        for col in range(min_col, max_col + 1):
            result.append(column_sums[col])
        
        return result
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
