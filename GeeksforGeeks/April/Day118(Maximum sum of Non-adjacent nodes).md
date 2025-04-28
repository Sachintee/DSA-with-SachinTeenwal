# *118. Maximum Sum of Non-Adjacent Nodes*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/maximum-sum-of-non-adjacent-nodes/1)


## **🧩 Problem Description**

Given a binary tree where each node has a positive integer value, the task is to find the **maximum sum of nodes** such that no two nodes are **directly connected** (i.e., if you pick a node, you cannot pick its parent or its immediate children).


## Code(C++)
```cpp
class Solution {
  public:
    pair<int,int> solve(Node* root) {
        if (!root) return {0,0};
        auto l = solve(root->left), r = solve(root->right);
        return {root->data+l.second+r.second, max(l.first,l.second)+max(r.first,r.second)};
    }
    int getMaxSum(Node* root) {
        auto p=solve(root);
        return max(p.first,p.second);
    }
};
```

## Code (Java)

```java
class Solution {
    int[] solve(Node r){
        if(r==null)return new int[]{0,0};
        int[] l=solve(r.left),r1=solve(r.right);
        return new int[]{r.data+l[1]+r1[1],Math.max(l[0],l[1])+Math.max(r1[0],r1[1])};
    }
    public int getMaxSum(Node r){
        int[] p=solve(r);
        return Math.max(p[0],p[1]);
    }
}
```

## Code (Python)

```python
class Solution:
    def solve(self,r):
        if not r: return (0,0)
        l,r1=self.solve(r.left),self.solve(r.right)
        return (r.data+l[1]+r1[1],max(l)+max(r1))
    def getMaxSum(self,root):
        return max(self.solve(root))
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
