---
title: "🔢 Longest Subarray Length | GFG Solution 🔍"
keywords🏷️: ["🔢 longest subarray", "🔍 stack", "📍 monotonic stack", "📈 next greater element", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Longest Subarray Length problem: find maximum length subarray where all elements are ≤ subarray length using monotonic stack technique. 🚀"
date: 📅 2025-09-20
---

# *263. Longest Subarray Length*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/longest-subarray-length--202010/1)

## **🧩 Problem Description**

You are given an array of integers `arr[]`. Your task is to find the length of the **longest subarray** such that all the elements of the subarray are **smaller than or equal to the length of the subarray**.

A subarray is a contiguous sequence of elements within an array. The goal is to find the maximum possible length where every element in the subarray satisfies: `element ≤ subarray_length`.


## Code(C++)
```cpp
class Solution {
public:
    int longestSubarray(vector<int>& a) {
        int n = a.size(), res = 0;
        vector<int> l(n, -1), r(n, n);
        stack<int> s;
        for (int i = n - 1; i >= 0; i--) {
            while (!s.empty() && a[s.top()] <= a[i]) s.pop();
            if (!s.empty()) r[i] = s.top();
            s.push(i);
        }
        while (!s.empty()) s.pop();
        for (int i = 0; i < n; i++) {
            while (!s.empty() && a[s.top()] <= a[i]) s.pop();
            if (!s.empty()) l[i] = s.top();
            s.push(i);
            int len = r[i] - l[i] - 1;
            if (len >= a[i]) res = max(res, len);
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public static int longestSubarray(int[] a) {
        int n = a.length, res = 0;
        int[] l = new int[n], r = new int[n];
        Arrays.fill(l, -1);
        Arrays.fill(r, n);
        Stack<Integer> s = new Stack<>();
        for (int i = n - 1; i >= 0; i--) {
            while (!s.empty() && a[s.peek()] <= a[i]) s.pop();
            if (!s.empty()) r[i] = s.peek();
            s.push(i);
        }
        s.clear();
        for (int i = 0; i < n; i++) {
            while (!s.empty() && a[s.peek()] <= a[i]) s.pop();
            if (!s.empty()) l[i] = s.peek();
            s.push(i);
            int len = r[i] - l[i] - 1;
            if (len >= a[i]) res = Math.max(res, len);
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def longestSubarray(self, a):
        n, res = len(a), 0
        l, r, s = [-1] * n, [n] * n, []
        for i in range(n - 1, -1, -1):
            while s and a[s[-1]] <= a[i]: s.pop()
            if s: r[i] = s[-1]
            s.append(i)
        s.clear()
        for i in range(n):
            while s and a[s[-1]] <= a[i]: s.pop()
            if s: l[i] = s[-1]
            s.append(i)
            length = r[i] - l[i] - 1
            if length >= a[i]: res = max(res, length)
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
