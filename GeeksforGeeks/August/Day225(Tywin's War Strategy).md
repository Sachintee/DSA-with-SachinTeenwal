---
title: "🏹 Tywin's War Strategy | GFG Solution 🎯"
keywords🏷️: ["🏹 tywin's war", "🎯 greedy algorithm", "📈 priority queue", "🔢 modular arithmetic", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to Tywin's War Strategy problem: find minimum soldiers to add to make at least ⌈n/2⌉ troops lucky using greedy approach with priority queue. 🚀"
date: 📅 2025-08-13
---

# *225. Tywin's War Strategy*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/tywins-war-strategy0527/1)

## **🧩 Problem Description**

You are given an array `arr[]` of size `n`, where `arr[i]` represents the number of soldiers in the i-th troop. You are also given an integer `k`. A troop is considered **"lucky"** if its number of soldiers is a multiple of `k`. Find the minimum total number of soldiers to add across all troops so that at least **⌈n / 2⌉** troops become lucky.

## **📘 Examples**

### Example 1


## Code(C++)
```cpp
class Solution {
public:
    int minSoldiers(vector<int>& arr, int k) {
        int n = arr.size(), need = (n + 1) / 2, total = 0;
        priority_queue<int, vector<int>, greater<int>> pq;
        for (int x : arr) pq.push(x % k ? k - x % k : 0);
        while (need--) total += pq.top(), pq.pop();
        return total;
    }
};
```

## Code (Java)

```java
class Solution {
    public int minSoldiers(int[] arr, int k) {
        int need = (arr.length + 1) / 2, total = 0;
        PriorityQueue<Integer> pq = new PriorityQueue<>();
        for (int x : arr) pq.offer(x % k == 0 ? 0 : k - x % k);
        while (need-- > 0) total += pq.poll();
        return total;
    }
}
```

## Code (Python)

```python
class Solution:
    def minSoldiers(self, arr, k):
        import heapq
        need, costs = (len(arr) + 1) // 2, []
        for x in arr: heapq.heappush(costs, 0 if x % k == 0 else k - x % k)
        return sum(heapq.heappop(costs) for _ in range(need))
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
