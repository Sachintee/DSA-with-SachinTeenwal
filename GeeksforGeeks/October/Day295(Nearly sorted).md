---
title: "🔢 Nearly Sorted | GFG Solution 🔍"
keywords🏷️: ["🔢 nearly sorted", "🔍 min heap", "📍 priority queue", "📈 sorting", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Nearly Sorted Array problem: efficiently sort an array where each element is at most k positions away from its target position using min heap. 🚀"
date: 📅 2025-10-22
---

# *295. Nearly Sorted*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/nearly-sorted-1587115620/1)

## **🧩 Problem Description**

You are given an array `arr[]`, where each element is at most `k` positions away from its correct position in the sorted order. Your task is to restore the sorted order of `arr[]` by rearranging the elements in place.

**Note:** Don't use any sort() method.

A nearly sorted array is one where each element is displaced by at most k positions from where it would be in a fully sorted array. The goal is to efficiently sort this array by leveraging this property.


## Code(C++)
```cpp
class Solution {
public:
    void nearlySorted(vector<int> &arr, int k) {
        priority_queue<int, vector<int>, greater<int>> pq(arr.begin(), arr.begin() + k);
        int idx = 0;
        for (int i = k; i < arr.size(); i++) {
            pq.push(arr[i]);
            arr[idx++] = pq.top();
            pq.pop();
        }
        while (!pq.empty()) {
            arr[idx++] = pq.top();
            pq.pop();
        }
    }
};
```

## Code (Java)

```java
class Solution {
    public void nearlySorted(int[] arr, int k) {
        PriorityQueue<Integer> pq = new PriorityQueue<>();
        int idx = 0, n = arr.length;
        for (int i = 0; i <= Math.min(k, n - 1); i++) pq.add(arr[i]);
        for (int i = k + 1; i < n; i++) {
            arr[idx++] = pq.poll();
            pq.add(arr[i]);
        }
        while (!pq.isEmpty()) arr[idx++] = pq.poll();
    }
}
```

## Code (Python)

```python
class Solution:
    def nearlySorted(self, arr, k):
        import heapq
        h = arr[:min(k + 1, len(arr))]
        heapq.heapify(h)
        idx = 0
        for i in range(k + 1, len(arr)):
            arr[idx] = heapq.heappop(h)
            heapq.heappush(h, arr[i])
            idx += 1
        while h:
            arr[idx] = heapq.heappop(h)
            idx += 1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
