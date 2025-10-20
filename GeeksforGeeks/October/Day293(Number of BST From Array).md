---
title: "🌳 Number of BST From Array | GFG Solution 🔍"
keywords🏷️: ["🌳 binary search tree", "🔢 catalan numbers", "📊 dynamic programming", "📈 combinatorics", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Number of BST From Array problem: count unique BSTs possible with each element as root using Catalan numbers and dynamic programming. 🚀"
date: 📅 2025-10-20
---

# *293. Number of BST From Array*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/number-of-bst-from-array/1)

## **🧩 Problem Description**

You are given an integer array `arr[]` containing distinct elements. Your task is to return an array where the **ith element** denotes the number of **unique BSTs** formed when `arr[i]` is chosen as the root.

In a Binary Search Tree (BST), all elements in the left subtree are smaller than the root, and all elements in the right subtree are greater than the root. The problem requires calculating how many structurally unique BSTs can be formed for each element when it serves as the root node.


## Code(C++)
```cpp
class Solution {
public:
    vector<int> countBSTs(vector<int>& arr) {
        int n = arr.size();
        vector<pair<int,int>> p(n);
        for (int i = 0; i < n; i++) p[i] = {arr[i], i};
        sort(p.begin(), p.end());
        vector<long> c(n + 1);
        c[0] = c[1] = 1;
        for (int i = 2; i <= n; i++) {
            for (int j = 0; j < i; j++) 
                c[i] += c[j] * c[i - j - 1];
        }
        vector<int> res(n);
        for (int i = 0; i < n; i++) 
            res[p[i].second] = c[i] * c[n - i - 1];
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<Integer> countBSTs(int[] arr) {
        int n = arr.length;
        int[][] p = new int[n][2];
        for (int i = 0; i < n; i++) {
            p[i][0] = arr[i];
            p[i][1] = i;
        }
        Arrays.sort(p, (a, b) -> a[0] - b[0]);
        long[] c = new long[n + 1];
        c[0] = c[1] = 1;
        for (int i = 2; i <= n; i++) {
            for (int j = 0; j < i; j++) 
                c[i] += c[j] * c[i - j - 1];
        }
        ArrayList<Integer> res = new ArrayList<>();
        for (int i = 0; i < n; i++) res.add(0);
        for (int i = 0; i < n; i++) 
            res.set(p[i][1], (int)(c[i] * c[n - i - 1]));
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def countBSTs(self, arr):
        n = len(arr)
        p = sorted((arr[i], i) for i in range(n))
        c = [0] * (n + 1)
        c[0] = c[1] = 1
        for i in range(2, n + 1):
            for j in range(i):
                c[i] += c[j] * c[i - j - 1]
        res = [0] * n
        for i in range(n):
            res[p[i][1]] = c[i] * c[n - i - 1]
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
