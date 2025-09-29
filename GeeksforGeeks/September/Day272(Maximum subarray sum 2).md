---
title: "💹 Maximum Subarray Sum with Length Constraints | GFG Solution 🔍"
keywords🏷️: ["💹 maximum subarray", "🔍 sliding window", "📍 monotonic deque", "📈 prefix sum", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Maximum Subarray Sum with Length Constraints problem: find maximum sum of subarray with length between a and b using monotonic deque optimization. 🚀"
date: 📅 2025-09-29
---

# *272. Maximum Subarray Sum 2*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/maximum-subarray-sum--110820/1)

## **🧩 Problem Description**

You are given an array `arr[]` of integers and two integers `a` and `b`. Your task is to find the **maximum possible sum** of a contiguous subarray whose length is **at least a** and **at most b**.

A subarray is a contiguous sequence of elements within an array. The goal is to efficiently find the maximum sum among all valid subarrays satisfying the length constraints.


## Code(C++)
```cpp
class Solution {
public:
    int maxSubarrSum(vector<int>& arr, int a, int b) {
        int n = arr.size(), res = INT_MIN;
        vector<int> pre(n + 1);
        for (int i = 0; i < n; i++) pre[i + 1] = pre[i] + arr[i];
        deque<int> dq;
        for (int i = a; i <= n; i++) {
            int l = max(0, i - b), r = i - a;
            while (!dq.empty() && pre[dq.back()] >= pre[r]) dq.pop_back();
            dq.push_back(r);
            while (!dq.empty() && dq.front() < l) dq.pop_front();
            res = max(res, pre[i] - pre[dq.front()]);
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public int maxSubarrSum(int[] arr, int a, int b) {
        int n = arr.length, res = Integer.MIN_VALUE;
        int[] pre = new int[n + 1];
        for (int i = 0; i < n; i++) pre[i + 1] = pre[i] + arr[i];
        Deque<Integer> dq = new ArrayDeque<>();
        for (int i = a; i <= n; i++) {
            int l = Math.max(0, i - b), r = i - a;
            while (!dq.isEmpty() && pre[dq.peekLast()] >= pre[r]) dq.pollLast();
            dq.offerLast(r);
            while (!dq.isEmpty() && dq.peekFirst() < l) dq.pollFirst();
            res = Math.max(res, pre[i] - pre[dq.peekFirst()]);
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def maxSubarrSum(self, arr, a, b):
        n, res = len(arr), float('-inf')
        pre = [0] * (n + 1)
        for i in range(n): pre[i + 1] = pre[i] + arr[i]
        dq = []
        for i in range(a, n + 1):
            l, r = max(0, i - b), i - a
            while dq and pre[dq[-1]] >= pre[r]: dq.pop()
            dq.append(r)
            while dq and dq[0] < l: dq.pop(0)
            res = max(res, pre[i] - pre[dq[0]])
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
