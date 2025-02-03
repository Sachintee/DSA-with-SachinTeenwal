---
Difficulty: Easy  
Source: 160 Days of Problem Solving  
Tags:
  - Tree
---

# 🚀 _Day 34. Height of Binary Tree_ 🧠

The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/tree-gfg-160/problem/height-of-binary-tree)

## 💡 **Problem Description:**

Given a binary tree, find its height.  
The height of a tree is defined as the number of edges on the longest path from the root to a leaf node.  
A leaf node is a node that does not have any children.


## Code(C++)
```cpp
#include <iostream>
#include <algorithm> // For std::max

// Node class definition
class Node {
public:
    int data;
    Node* left;
    Node* right;
    
    Node(int val) {
        data = val;
        left = right = nullptr;
    }
};

class Solution {
public:
    // Function to find the height of a binary tree.
    int height(Node* root) {
        if (root == nullptr) {
            return -1;
        }
        int leftHeight = height(root->left);
        int rightHeight = height(root->right);
        return 1 + std::max(leftHeight, rightHeight);
    }
};

// Example usage
int main() {
    // Creating a binary tree
    Node* root = new Node(1);
    root->left = new Node(2);
    root->right = new Node(3);
    root->left->left = new Node(4);
    root->left->right = new Node(5);
    
    Solution solution;
    std::cout << "Height of the tree is: " << solution.height(root) << std::endl;
    
    return 0;
}
```

## Code (Java)

```java
// Node class definition
class Node {
    int data;
    Node left, right;
    
    Node(int val) {
        data = val;
        left = right = null;
    }
}

class Solution {
    // Function to find the height of a binary tree.
    int height(Node root) {
        if (root == null) {
            return -1;
        }
        int leftHeight = height(root.left);
        int rightHeight = height(root.right);
        return 1 + Math.max(leftHeight, rightHeight);
    }
}

// Example usage
public class Main {
    public static void main(String[] args) {
        // Creating a binary tree
        Node root = new Node(1);
        root.left = new Node(2);
        root.right = new Node(3);
        root.left.left = new Node(4);
        root.left.right = new Node(5);
        
        Solution solution = new Solution();
        System.out.println("Height of the tree is: " + solution.height(root));
    }
}
```

## Code (Python)

```python
#User function Template for python3

'''
# Node Class:
class Node:
    def _init_(self,val):
        self.data = val
        self.left = None
        self.right = None
'''
class Solution:
    #Function to find the height of a binary tree.
    def height(self, root):
        # code here
        if root is None:
            return -1
        left_height = self.height(root.left)
        right_height = self.height(root.right)
        return 1 + max(left_height, right_height)
            


```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
