---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Tree
---

# 🚀 _Day 35. Diameter of a Binary Tree_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/tree-gfg-160/problem/diameter-of-binary-tree)

## 💡 **Problem Description:**

Given a binary tree, the diameter (or width) is defined as the number of edges on the longest path between two leaf nodes in the tree. This path may or may not pass through the root. Your task is to determine the diameter of the tree.


## Code(C++)
```cpp
#include <iostream>
#include <algorithm> // For std::max
using namespace std;

// Tree Node
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
    int diameter(Node* root) {
        int dia = 0;
        helper(root, dia);
        return dia;
    }

private:
    int helper(Node* root, int& dia) {
        if (!root) {
            return 0;
        }
        // Recursively find the height of the left and right subtrees
        int leftHeight = helper(root->left, dia);
        int rightHeight = helper(root->right, dia);

        // Update the diameter if the current path is longer
        dia = max(dia, leftHeight + rightHeight);

        // Return the height of the current subtree
        return 1 + max(leftHeight, rightHeight);
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
    cout << "Diameter of the tree is: " << solution.diameter(root) << endl; // Output: 3

    return 0;
}
```

## Code (Java)

```java
// Tree Node
class Node {
    int data;
    Node left, right;

    Node(int val) {
        data = val;
        left = right = null;
    }
}

class Solution {
    private int dia = 0;

    public int diameter(Node root) {
        helper(root);
        return dia;
    }

    private int helper(Node root) {
        if (root == null) {
            return 0;
        }
        // Recursively find the height of the left and right subtrees
        int leftHeight = helper(root.left);
        int rightHeight = helper(root.right);

        // Update the diameter if the current path is longer
        dia = Math.max(dia, leftHeight + rightHeight);

        // Return the height of the current subtree
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
        System.out.println("Diameter of the tree is: " + solution.diameter(root)); // Output: 3
    }
}
```

## Code (Python)

```python
'''
# Tree Node
class Node:

    def __init__(self, val):
        self.right = None
        self.data = val
        self.left = None
'''
class Solution:
    def diameter(self, root):
        # Your code here
        def helper(root):
            if not root:
                return 0
            left=helper(root.left)
            right=helper(root.right)
            self.dia=max(self.dia,left+right)
            return 1+max(left,right)
        self.dia=0
        helper(root)
        return self.dia
        
        

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
