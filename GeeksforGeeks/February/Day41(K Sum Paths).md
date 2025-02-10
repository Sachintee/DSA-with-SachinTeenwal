---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Tree
---

# 🚀 _Day 41. K Sum Paths_ 🧠

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/tree-gfg-160/problem/k-sum-paths)  

## 💡 **Problem Description:**

Given a binary tree and an integer **k**, determine the number of downward-only paths where the sum of the node values in the path equals **k**.  
A path can start and end at any node within the tree but must always move downward (from parent to child).

## Code(C++)
```cpp
class Solution {
public:
    unordered_map<int, int> m;
    int cnt = 0;
    void dfs(Node* node, int k, int currSum) {
        if (!node) return;
        currSum += node->data;
        if (m.count(currSum - k))
            cnt += m[currSum - k];
        m[currSum]++;
        dfs(node->left, k, currSum);
        dfs(node->right, k, currSum);
        m[currSum]--;
    }
    int sumK(Node* root, int k) {
        m[0] = 1;
        dfs(root, k, 0);
        return cnt;
    }
};
```

## Code (Java)

```java
class Solution {
    Map<Integer,Integer> m = new HashMap<>();
    int cnt = 0;
    void dfs(Node r, int k, int s) {
        if(r==null)return;
        s += r.data;
        if(m.containsKey(s-k)) cnt += m.get(s-k);
        m.put(s, m.getOrDefault(s,0)+1);
        dfs(r.left, k, s);
        dfs(r.right, k, s);
        m.put(s, m.get(s)-1);
        if(m.get(s)==0)m.remove(s);
    }
    public int sumK(Node r, int k) {
        m.put(0,1);
        dfs(r, k, 0);
        return cnt;
    }
}
```

## Code (Python)

```python
class Solution:
    def sumK(self, r, k):
        self.c = 0
        m = {0: 1}
        def dfs(r, s):
            if not r: return
            s += r.data
            self.c += m.get(s - k, 0)
            m[s] = m.get(s, 0) + 1
            dfs(r.left, s)
            dfs(r.right, s)
            m[s] -= 1
            if m[s] == 0: del m[s]
        dfs(r, 0)
        return self.c
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
