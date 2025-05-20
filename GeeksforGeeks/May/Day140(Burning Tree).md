# *140. Burning Tree*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/burning-tree/1)

## **🧩 Problem Description**

You are given a binary tree and a target node. The task is to determine the minimum time required to burn the entire tree if the fire starts from the target node.

In each time unit, the fire spreads to adjacent nodes: the parent, left child, and right child of a burning node.


## Code(C++)
```cpp
class Solution {
public:
    int ans;
    pair<int,int> dfs(Node* r,int t){
        if(!r) return {0,-1};
        auto l=dfs(r->left,t), ri=dfs(r->right,t);
        int h=max(l.first,ri.first)+1, d=-1;
        if(r->data==t) d=0, ans=max(ans,h-1);
        else if(l.second>=0) d=l.second+1, ans=max(ans,ri.first+d);
        else if(ri.second>=0) d=ri.second+1, ans=max(ans,l.first+d);
        return {h,d};
    }
    int minTime(Node* root,int target){
        ans=0;
        dfs(root,target);
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    static int ans;
    public static int minTime(Node root,int t){
        ans=0;
        dfs(root,t);
        return ans;
    }
    static int[] dfs(Node r,int t){
        if(r==null) return new int[]{0,-1};
        int[] l=dfs(r.left,t), ri=dfs(r.right,t);
        int h=Math.max(l[0],ri[0])+1, d=-1;
        if(r.data==t){ d=0; ans=Math.max(ans,h-1); }
        else if(l[1]>=0){ d=l[1]+1; ans=Math.max(ans,ri[0]+d); }
        else if(ri[1]>=0){ d=ri[1]+1; ans=Math.max(ans,l[0]+d); }
        return new int[]{h,d};
    }
}
```

## Code (Python)

```python
class Solution:
    def minTime(self, root, target):
        self.ans = 0
        def dfs(r):
            if not r: return (0, -1)
            l0, l1 = dfs(r.left)
            r0, r1 = dfs(r.right)
            h = max(l0, r0) + 1
            d = -1
            if r.data == target:
                d = 0
                self.ans = max(self.ans, h-1)
            elif l1 >= 0:
                d = l1 + 1
                self.ans = max(self.ans, r0 + d)
            elif r1 >= 0:
                d = r1 + 1
                self.ans = max(self.ans, l0 + d)
            return (h, d)
        dfs(root)
        return self.ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
