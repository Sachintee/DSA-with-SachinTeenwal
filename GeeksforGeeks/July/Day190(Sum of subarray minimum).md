---
title: "➕ Sum of Subarray Minimums | GFG Solution 🔍"
keywords🏷️: ["➕ sum of subarray minimums", "🔍 monotonic stack", "📍 contribution technique", "📈 stack", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Sum of Subarray Minimums problem: find the total sum of minimum elements in all subarrays using monotonic stack and contribution technique. 🚀"
date: 📅 2025-07-09
---

# *190. Sum of Subarray Minimums*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/sum-of-subarray-minimum/1)

## **🧩 Problem Description**

Given an array `arr[]` of positive integers, find the **total sum of the minimum elements** of every possible subarrays.

A subarray is a contiguous sequence of elements within an array. For each subarray, we need to find its minimum element and sum all these minimum values.


## Code(C++)
```cpp
class Solution {
public:
    int sumSubMins(vector<int>& arr) {
        const int MOD = 1e9 + 7;
        int n = arr.size();
        vector<int> left(n), right(n);
        stack<int> st;
        for (int i = 0; i < n; i++) {
            while (!st.empty() && arr[st.top()] >= arr[i]) st.pop();
            left[i] = st.empty() ? i + 1 : i - st.top();
            st.push(i);
        }
        while (!st.empty()) st.pop();
        for (int i = n - 1; i >= 0; i--) {
            while (!st.empty() && arr[st.top()] > arr[i]) st.pop();
            right[i] = st.empty() ? n - i : st.top() - i;
            st.push(i);
        }
        long long res = 0;
        for (int i = 0; i < n; i++) {
            res = (res + (long long)arr[i] * left[i] * right[i]) % MOD;
        }
        return res;
    }
};
```

## Code (Java)

```java
\class Solution {
    public int sumSubMins(int[] arr) {
        final int MOD = 1000000007;
        int n = arr.length;
        int[] left = new int[n];
        int[] right = new int[n];
        Deque<Integer> st = new ArrayDeque<>();
        for (int i = 0; i < n; i++) {
            while (!st.isEmpty() && arr[st.peekLast()] >= arr[i]) st.pollLast();
            left[i] = st.isEmpty() ? i + 1 : i - st.peekLast();
            st.offerLast(i);
        }
        st.clear();
        for (int i = n - 1; i >= 0; i--) {
            while (!st.isEmpty() && arr[st.peekLast()] > arr[i]) st.pollLast();
            right[i] = st.isEmpty() ? n - i : st.peekLast() - i;
            st.offerLast(i);
        }
        long res = 0;
        for (int i = 0; i < n; i++) {
            res = (res + (long) arr[i] * left[i] * right[i]) % MOD;
        }
        return (int) res;
    }
}
```

## Code (Python)

```python
class Solution:
    def sumSubMins(self, arr):
        MOD = 10**9 + 7
        n = len(arr)
        left = [0] * n
        right = [0] * n
        st = []
        for i in range(n):
            while st and arr[st[-1]] >= arr[i]:
                st.pop()
            left[i] = i + 1 if not st else i - st[-1]
            st.append(i)
        st.clear()
        for i in range(n - 1, -1, -1):
            while st and arr[st[-1]] > arr[i]:
                st.pop()
            right[i] = n - i if not st else st[-1] - i
            st.append(i)
        return sum(arr[i] * left[i] * right[i] for i in range(n)) % MOD
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
