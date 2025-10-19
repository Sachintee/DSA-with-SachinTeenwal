---
title: "🌲 K Closest Values | GFG Solution 🎯"
keywords🏷️: ["🌲 binary search tree", "🎯 k closest", "📍 two pointers", "🔍 inorder traversal", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the K Closest Values in BST problem: find k values closest to target using iterative inorder traversal and two-pointer technique. 🚀"
date: 📅 2025-10-19
---

# *292. K Closest Values*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/k-closest-values/1)

## **🧩 Problem Description**

Given the root of a **Binary Search Tree**, a target value, and an integer `k`, your task is to find the **k values** in the BST that are **closest to the target**.

The closest value is determined by the **minimum absolute difference** from the target. If two values have the same absolute difference, choose the **smaller value**. The target may or may not be present in the BST.


## Code(C++)
```cpp
class Solution {
public:
    vector<int> getKClosest(Node* root, int target, int k) {
        vector<int> in;
        stack<Node*> s;
        Node* curr = root;
        while (curr || !s.empty()) {
            while (curr) s.push(curr), curr = curr->left;
            curr = s.top(); s.pop();
            in.push_back(curr->data);
            curr = curr->right;
        }
        int n = in.size(), pos = lower_bound(in.begin(), in.end(), target) - in.begin();
        if (pos > 0 && (pos == n || abs(in[pos - 1] - target) <= abs(in[pos] - target))) pos--;
        vector<int> res;
        int l = pos, r = pos + 1;
        while (k--) {
            if (r >= n || (l >= 0 && abs(in[l] - target) <= abs(in[r] - target)))
                res.push_back(in[l--]);
            else
                res.push_back(in[r++]);
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<Integer> getKClosest(Node root, int target, int k) {
        ArrayList<Integer> in = new ArrayList<>();
        Stack<Node> s = new Stack<>();
        Node curr = root;
        while (curr != null || !s.isEmpty()) {
            while (curr != null) {
                s.push(curr);
                curr = curr.left;
            }
            curr = s.pop();
            in.add(curr.data);
            curr = curr.right;
        }
        int n = in.size(), l = 0, r = n - 1, pos = 0;
        while (l <= r) {
            int m = l + (r - l) / 2;
            if (in.get(m) <= target) {
                pos = m;
                l = m + 1;
            } else r = m - 1;
        }
        ArrayList<Integer> res = new ArrayList<>();
        l = pos; r = pos + 1;
        while (k-- > 0) {
            if (r >= n || (l >= 0 && Math.abs(in.get(l) - target) <= Math.abs(in.get(r) - target)))
                res.add(in.get(l--));
            else
                res.add(in.get(r++));
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def getKClosest(self, root, target, k):
        in_order, stack, curr = [], [], root
        while curr or stack:
            while curr:
                stack.append(curr)
                curr = curr.left
            curr = stack.pop()
            in_order.append(curr.data)
            curr = curr.right
        n, l, r, pos = len(in_order), 0, len(in_order) - 1, 0
        while l <= r:
            m = (l + r) // 2
            if in_order[m] <= target:
                pos, l = m, m + 1
            else:
                r = m - 1
        res, l, r = [], pos, pos + 1
        while k:
            if r >= n or (l >= 0 and abs(in_order[l] - target) <= abs(in_order[r] - target)):
                res.append(in_order[l])
                l -= 1
            else:
                res.append(in_order[r])
                r += 1
            k -= 1
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
