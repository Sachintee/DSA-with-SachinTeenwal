---
title: "🔗 Minimum Cost of Ropes | GFG Solution 🎯"
keywords🏷️: ["🔗 minimum cost", "🌳 min heap", "⚡ greedy algorithm", "📊 priority queue", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Minimum Cost of Ropes problem: find minimum total cost to connect all ropes using greedy approach with min-heap. 🚀"
date: 📅 2025-10-26
---

# *299. Minimum Cost of Ropes*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/minimum-cost-of-ropes-1587115620/1)

## **🧩 Problem Description**

You are given an array `arr[]` of rope lengths. Your task is to connect all ropes into a single rope with the **minimum total cost**. The cost to connect two ropes is equal to the sum of their lengths.

The goal is to find the optimal order of connecting ropes to minimize the total cost of all connections.


## Code(C++)
```cpp
class Solution {
public:
    int minCost(vector<int>& arr) {
        priority_queue<int, vector<int>, greater<int>> pq(arr.begin(), arr.end());
        int res = 0;
        while (pq.size() > 1) {
            int first = pq.top(); pq.pop();
            int second = pq.top(); pq.pop();
            res += first + second;
            pq.push(first + second);
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public static int minCost(int[] arr) {
        PriorityQueue<Integer> pq = new PriorityQueue<>();
        for (int x : arr) pq.add(x);
        int res = 0;
        while (pq.size() > 1) {
            int sum = pq.poll() + pq.poll();
            res += sum;
            pq.add(sum);
        }
        return res;
    }
}
```

## Code (Python)

```python
import heapq

class Solution:
    def minCost(self, arr):
        heapq.heapify(arr)
        res = 0
        while len(arr) > 1:
            sum_val = heapq.heappop(arr) + heapq.heappop(arr)
            res += sum_val
            heapq.heappush(arr, sum_val)
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
