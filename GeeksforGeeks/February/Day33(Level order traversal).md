---
Difficulty: Easy  
Source: 160 Days of Problem Solving  
Tags:
  - Tree
---
# 🚀 _Day 33. Level order traversal
_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/tree-gfg-160/problem/level-order-traversal)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <vector>
#include <queue>

using namespace std;

// Definition for a binary tree node.
class Node {
public:
    int data;
    Node* left;
    Node* right;
    
    Node(int value) {
        data = value;
        left = right = nullptr;
    }
};

class Solution {
public:
    vector<vector<int>> levelOrder(Node* root) {
        vector<vector<int>> ans;
        if (!root) return ans;
        
        queue<Node*> q;
        q.push(root);
        
        while (!q.empty()) {
            int n = q.size();
            vector<int> currLevel;
            
            for (int i = 0; i < n; i++) {
                Node* node = q.front();
                q.pop();
                currLevel.push_back(node->data);
                
                if (node->left) q.push(node->left);
                if (node->right) q.push(node->right);
            }
            ans.push_back(currLevel);
        }
        return ans;
    }
};

// Driver Code
int main() {
    Node* root = new Node(1);
    root->left = new Node(2);
    root->right = new Node(3);
    root->left->left = new Node(4);
    root->left->right = new Node(5);
    
    Solution obj;
    vector<vector<int>> result = obj.levelOrder(root);
    
    for (const auto& level : result) {
        for (int val : level) {
            cout << val << " ";
        }
        cout << endl;
    }
    return 0;
}

```

## Code (Java)

```java
import java.util.*;

class Node {
    int data;
    Node left, right;
    
    public Node(int value) {
        data = value;
        left = right = null;
    }
}

class Solution {
    public List<List<Integer>> levelOrder(Node root) {
        List<List<Integer>> ans = new ArrayList<>();
        if (root == null) return ans;
        
        Queue<Node> q = new LinkedList<>();
        q.add(root);
        
        while (!q.isEmpty()) {
            int n = q.size();
            List<Integer> currLevel = new ArrayList<>();
            
            for (int i = 0; i < n; i++) {
                Node node = q.poll();
                currLevel.add(node.data);
                
                if (node.left != null) q.add(node.left);
                if (node.right != null) q.add(node.right);
            }
            ans.add(new ArrayList<>(currLevel));
        }
        return ans;
    }

    public static void main(String[] args) {
        Node root = new Node(1);
        root.left = new Node(2);
        root.right = new Node(3);
        root.left.left = new Node(4);
        root.left.right = new Node(5);

        Solution obj = new Solution();
        List<List<Integer>> result = obj.levelOrder(root);

        for (List<Integer> level : result) {
            System.out.println(level);
        }
    }
}

```

## Code (Python)

```python
"""
class Node:
    def __init__(self, value):
        self.left = None
        self.data = value
        self.right = None
"""
class Solution:
    def levelOrder(self, root):
        # Your code here
        q=deque()
        q.append(root)
        ans=[]
        while q:
            n=len(q)
            curr=[]
            for _ in range(n):
                node=q.popleft()
                curr.append(node.data)
                if node.left:
                    q.append(node.left)
                if node.right:
                    q.append(node.right)
            ans.append(curr.copy())
        return ans

        

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
