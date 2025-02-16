---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Tree
---

# 🚀 _Day 47. Serialize and deserialize a binary tree_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/tree-gfg-160/problem/serialize-and-deserialize-a-binary-tree)  

## 💡 **Problem Description:**

Serialization is the process of converting a **binary tree** into an **array** so it can be stored or transmitted efficiently.  
Deserialization is the process of **reconstructing the tree** back from the serialized array.  


## Code(C++)
```cpp
class Solution {
  public:
    void serializeUtil(Node *root, vector<int> &a) {
        if (!root) { a.push_back(-1); return; }
        a.push_back(root->data);
        serializeUtil(root->left, a);
        serializeUtil(root->right, a);
    }

    vector<int> serialize(Node *root) {
        vector<int> a;
        serializeUtil(root, a);
        return a;
    }

    Node *buildTree(vector<int> &a, int &i) {
        if (i >= a.size() || a[i] == -1) return i++, nullptr;
        Node *root = new Node(a[i++]);
        root->left = buildTree(a, i);
        root->right = buildTree(a, i);
        return root;
    }

    Node *deSerialize(vector<int> &a) {
        int i = 0;
        return buildTree(a, i);
    }
};
```

## Code (Java)

```java
class Tree {
    public ArrayList<Integer> serialize(Node r) {
        ArrayList<Integer> a = new ArrayList<>();
        s(r, a);
        return a;
    }
    void s(Node r, ArrayList<Integer> a) {
        if(r==null){a.add(-1); return;}
        a.add(r.data);
        s(r.left, a);
        s(r.right, a);
    }
    public Node deSerialize(ArrayList<Integer> a) {
        int[] i = {0};
        return d(a, i);
    }
    Node d(ArrayList<Integer> a, int[] i) {
        if(i[0]>=a.size() || a.get(i[0])==-1){i[0]++; return null;}
        Node r = new Node(a.get(i[0]++));
        r.left = d(a, i);
        r.right = d(a, i);
        return r;
    }
}
```

## Code (Python)

```python
class Solution:
    def serialize(self, root):
        a = []
        def s(r):
            if not r:
                a.append(-1)
                return
            a.append(r.data)
            s(r.left)
            s(r.right)
        s(root)
        return a

    def deSerialize(self, arr):
        self.i = 0
        def d():
            if self.i >= len(arr) or arr[self.i] == -1:
                self.i += 1
                return None
            r = Node(arr[self.i])
            self.i += 1
            r.left = d()
            r.right = d()
            return r
        return d()
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
