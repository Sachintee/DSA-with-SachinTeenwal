---
title: "⚖️ Minimum Steps to Halve Sum | GFG Solution 🔍"
keywords🏷️: ["⚖️ minimum operations", "🔍 greedy algorithm", "📍 priority queue", "📈 heap", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Minimum Steps to Halve Sum problem: find minimum operations to reduce array sum to half or less by repeatedly halving the largest element using greedy heap approach. 🚀"
date: 📅 2025-10-25
---

# *298. Minimum Steps to Halve Sum*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/minimum-steps-to-halve-sum/1)

## **🧩 Problem Description**

You are given an array `arr[]` consisting of positive integers. Your task is to find the **minimum number of operations** required to make the sum of its elements **less than or equal to half** of the original sum. In one operation, you may replace any element with half of its value (with floating-point precision).

The goal is to minimize the number of operations needed to achieve this target sum by strategically choosing which elements to halve.


## Code(C++)
```cpp
class Solution {
public:
    int minOperations(vector<int>& arr) {
        double s = accumulate(arr.begin(), arr.end(), 0.0), t = s / 2;
        priority_queue<double> q(arr.begin(), arr.end());
        int ops = 0;
        while (s > t) {
            double x = q.top(); q.pop();
            s -= x / 2;
            q.push(x / 2);
            ops++;
        }
        return ops;
    }
};
```

## Code (Java)

```java
class Solution {
    public int minOperations(int[] arr) {
        double s = 0, t;
        PriorityQueue<Double> q = new PriorityQueue<>(Collections.reverseOrder());
        for (int x : arr) {
            s += x;
            q.offer((double) x);
        }
        t = s / 2;
        int ops = 0;
        while (s > t) {
            double x = q.poll();
            s -= x / 2;
            q.offer(x / 2);
            ops++;
        }
        return ops;
    }
}
```

## Code (Python)

```python
class Solution:
    def minOperations(self, arr):
        import heapq
        s = sum(arr)
        t = s / 2
        h = [-x for x in arr]
        heapq.heapify(h)
        ops = 0
        while s > t:
            x = -heapq.heappop(h)
            s -= x / 2
            heapq.heappush(h, -x / 2)
            ops += 1
        return ops
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
