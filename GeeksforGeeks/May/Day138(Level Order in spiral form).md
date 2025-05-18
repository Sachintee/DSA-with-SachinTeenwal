--- ❤️ ---

# 🚀 _Day 138. Level Order in spiral form_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/problems/level-order-traversal-in-spiral-form/1)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
  public:
    vector<int> findSpiral(Node* root) {
        vector<int> result;
        if (!root) return result;
        
        stack<Node*> s1; // For even levels: right to left
        stack<Node*> s2; // For odd levels: left to right
        
        s1.push(root);
        
        while (!s1.empty() || !s2.empty()) {
            // Process current level from s1
            while (!s1.empty()) {
                Node* curr = s1.top();
                s1.pop();
                result.push_back(curr->data);
                
                // For next level, left child goes after right (right to left)
                if (curr->right) s2.push(curr->right);
                if (curr->left) s2.push(curr->left);
            }
            
            // Process current level from s2
            while (!s2.empty()) {
                Node* curr = s2.top();
                s2.pop();
                result.push_back(curr->data);
                
                // For next level, right child goes after left (left to right)
                if (curr->left) s1.push(curr->left);
                if (curr->right) s1.push(curr->right);
            }
        }
        
        return result;
    }
};

```

## Code (Java)

```java
// Tree Node class
class Node {
    int data;
    Node left, right;

    Node(int item) {
        data = item;
        left = right = null;
    }
}

// Solution class
class Solution {
    ArrayList<Integer> findSpiral(Node root) {
        ArrayList<Integer> result = new ArrayList<>();
        if (root == null) return result;

        Stack<Node> s1 = new Stack<>(); // Even levels (right to left)
        Stack<Node> s2 = new Stack<>(); // Odd levels (left to right)

        s1.push(root);

        while (!s1.isEmpty() || !s2.isEmpty()) {
            while (!s1.isEmpty()) {
                Node node = s1.pop();
                result.add(node.data);

                // Push children for the next level in reverse order
                if (node.right != null) s2.push(node.right);
                if (node.left != null) s2.push(node.left);
            }

            while (!s2.isEmpty()) {
                Node node = s2.pop();
                result.add(node.data);

                // Push children for the next level in reverse order
                if (node.left != null) s1.push(node.left);
                if (node.right != null) s1.push(node.right);
            }
        }

        return result;
    }
}

```

## Code (Python)

```python
# Tree Node class
class Node:
    def __init__(self, data):
        self.data = data
        self.left = self.right = None

class Solution:
    def findSpiral(self, root):
        if not root:
            return []

        result = []
        s1 = [root]  # Even levels (right to left)
        s2 = []      # Odd levels (left to right)

        while s1 or s2:
            # Process even level (right to left)
            while s1:
                node = s1.pop()
                result.append(node.data)
                if node.right:
                    s2.append(node.right)
                if node.left:
                    s2.append(node.left)

            # Process odd level (left to right)
            while s2:
                node = s2.pop()
                result.append(node.data)
                if node.left:
                    s1.append(node.left)
                if node.right:
                    s1.append(node.right)

        return result

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
