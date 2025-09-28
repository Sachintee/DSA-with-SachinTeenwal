---
title: "📏 Longest Bounded-Difference Subarray | GFG Solution 🔍"
keywords🏷️: ["📏 longest subarray", "🔍 sliding window", "📍 two pointers", "🔄 monotonic deque", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Longest Bounded-Difference Subarray problem: find maximum length subarray where absolute difference between any two elements ≤ x using monotonic deque technique. 🚀"
date: 📅 2025-09-28
---

# *271. Longest Bounded-Difference Subarray*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/longest-bounded-difference-subarray/1)

## **🧩 Problem Description**

Given an array of positive integers `arr[]` and a non-negative integer `x`, the task is to find the **longest sub-array** where the **absolute difference between any two elements** is not greater than `x`.

If multiple such subarrays exist, return the one that starts at the **smallest index**.

A subarray is considered valid if for any two elements `arr[i]` and `arr[j]` in the subarray, `|arr[i] - arr[j]| ≤ x`.


## Code(C++)
```cpp
class Solution {
public:
    vector<int> longestSubarray(vector<int>& arr, int x) {
        deque<int> minQ, maxQ;
        int n = arr.size(), l = 0, r = 0, start = 0, len = 0;
        while (r < n) {
            while (!minQ.empty() && arr[minQ.back()] >= arr[r]) minQ.pop_back();
            while (!maxQ.empty() && arr[maxQ.back()] <= arr[r]) maxQ.pop_back();
            minQ.push_back(r);
            maxQ.push_back(r);
            while (arr[maxQ.front()] - arr[minQ.front()] > x) {
                if (l == minQ.front()) minQ.pop_front();
                if (l == maxQ.front()) maxQ.pop_front();
                l++;
            }
            if (r - l + 1 > len) {
                len = r - l + 1;
                start = l;
            }
            r++;
        }
        return vector<int>(arr.begin() + start, arr.begin() + start + len);
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<Integer> longestSubarray(int[] arr, int x) {
        ArrayDeque<Integer> minQ = new ArrayDeque<>(), maxQ = new ArrayDeque<>();
        int n = arr.length, l = 0, start = 0, maxLen = 0;
        for (int r = 0; r < n; r++) {
            while (!minQ.isEmpty() && arr[minQ.peekLast()] >= arr[r]) minQ.removeLast();
            while (!maxQ.isEmpty() && arr[maxQ.peekLast()] <= arr[r]) maxQ.removeLast();
            minQ.addLast(r);
            maxQ.addLast(r);
            while (arr[maxQ.peekFirst()] - arr[minQ.peekFirst()] > x) {
                if (l == minQ.peekFirst()) minQ.removeFirst();
                if (l == maxQ.peekFirst()) maxQ.removeFirst();
                l++;
            }
            if (r - l + 1 > maxLen) {
                maxLen = r - l + 1;
                start = l;
            }
        }
        ArrayList<Integer> result = new ArrayList<>();
        for (int i = start; i < start + maxLen; i++) result.add(arr[i]);
        return result;
    }
}
```

## Code (Python)

```python
class Solution:
    def longestSubarray(self, arr, x):
        from collections import deque
        minQ, maxQ = deque(), deque()
        n, l, start, maxLen = len(arr), 0, 0, 0
        for r in range(n):
            while minQ and arr[minQ[-1]] >= arr[r]: minQ.pop()
            while maxQ and arr[maxQ[-1]] <= arr[r]: maxQ.pop()
            minQ.append(r)
            maxQ.append(r)
            while arr[maxQ[0]] - arr[minQ[0]] > x:
                if l == minQ[0]: minQ.popleft()
                if l == maxQ[0]: maxQ.popleft()
                l += 1
            if r - l + 1 > maxLen:
                maxLen = r - l + 1
                start = l
        return arr[start:start + maxLen]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
