# *147. Print Leaf Nodes from Preorder Traversal of BST*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/print-leaf-nodes-from-preorder-traversal-of-bst2657/1)

## **🧩 Problem Description**

Given the preorder traversal of a Binary Search Tree (BST), print all the leaf nodes of this BST **without** actually reconstructing the tree.

### ❗Note:

* It is guaranteed that the input preorder is of a **valid BST**.
* The output order must follow the **order of the leaf nodes as they appear during preorder traversal**.


## Code(C++)
```cpp
class Solution {
  public:
    vector<int> leafNodes(vector<int>& p) {
        stack<int> s;
        vector<int> r;
        for (int i = 0, j = 1; j < p.size(); i++, j++) {
            bool f = 0;
            if (p[i] > p[j]) s.push(p[i]);
            else while (!s.empty() && p[j] > s.top()) s.pop(), f = 1;
            if (f) r.push_back(p[i]);
        }
        r.push_back(p.back());
        return r;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<Integer> leafNodes(int[] p) {
        Stack<Integer> st = new Stack<>();
        ArrayList<Integer> r = new ArrayList<>();
        for (int i = 0, j = 1; j < p.length; i++, j++) {
            boolean f = false;
            if (p[i] > p[j]) st.push(p[i]);
            else {
                while (!st.isEmpty() && p[j] > st.peek()) {
                    st.pop();
                    f = true;
                }
            }
            if (f) r.add(p[i]);
        }
        r.add(p[p.length-1]);
        return r;
    }
}
```

## Code (Python)

```python
class Solution:
    def leafNodes(self, preorder):
        s, r = [], []
        for i in range(len(preorder)-1):
            f = False
            if preorder[i] > preorder[i+1]:
                s.append(preorder[i])
            else:
                while s and preorder[i+1] > s[-1]:
                    s.pop()
                    f = True
            if f:
                r.append(preorder[i])
        r.append(preorder[-1])
        return r
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
