---
title: "📏 Max of Min for Every Window Size | GFG Solution 📊"
keywords🏷️: ["📏 window size", "📊 stack optimization", "📈 monotonic stack", "🔍 sliding window", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Max of Min for Every Window Size problem: find maximum of minimum values for all possible window sizes using monotonic stack technique. 🚀"
date: 📅 2025-09-22
---

# *265. Max of Min for Every Window Size*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/maximum-of-minimum-for-every-window-size3453/1)

## **🧩 Problem Description**

You are given an integer array `arr[]`. The task is to find the **maximum of minimum values** for every window size `k` where `1 ≤ k ≤ arr.size()`.

For each window size `k`, consider all contiguous subarrays of length `k`, determine the minimum element in each subarray, and then take the maximum among all these minimums.

Return the results as an array, where the element at index `i` represents the answer for window size `i+1`.


## Code(C++)
```cpp
class Solution {
public:
    vector<int> maxOfMins(vector<int>& a) {
        int n = a.size();
        vector<int> ans(n), mx(n + 1);
        stack<int> st;
        
        for (int i = 0; i <= n; i++) {
            while (!st.empty() && (i == n || a[st.top()] >= a[i])) {
                int mid = st.top(); st.pop();
                int w = i - (st.empty() ? -1 : st.top()) - 1;
                mx[w] = max(mx[w], a[mid]);
            }
            st.push(i);
        }
        
        for (int i = 1; i <= n; i++) ans[i-1] = mx[i];
        for (int i = n-2; i >= 0; i--) ans[i] = max(ans[i], ans[i+1]);
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<Integer> maxOfMins(int[] a) {
        int n = a.length;
        ArrayList<Integer> ans = new ArrayList<>();
        int[] mx = new int[n + 1];
        Stack<Integer> st = new Stack<>();
        
        for (int i = 0; i <= n; i++) {
            while (!st.isEmpty() && (i == n || a[st.peek()] >= a[i])) {
                int mid = st.pop();
                int w = i - (st.isEmpty() ? -1 : st.peek()) - 1;
                mx[w] = Math.max(mx[w], a[mid]);
            }
            st.push(i);
        }
        
        for (int i = 1; i <= n; i++) ans.add(mx[i]);
        for (int i = n - 2; i >= 0; i--) {
            ans.set(i, Math.max(ans.get(i), ans.get(i + 1)));
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def maxOfMins(self, a):
        n = len(a)
        ans, mx, st = [], [0] * (n + 1), []
        
        for i in range(n + 1):
            while st and (i == n or a[st[-1]] >= a[i]):
                mid = st.pop()
                w = i - (st[-1] if st else -1) - 1
                mx[w] = max(mx[w], a[mid])
            st.append(i)
        
        ans = mx[1:n+1]
        for i in range(n - 2, -1, -1):
            ans[i] = max(ans[i], ans[i + 1])
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐ #dsa @dsa

---
