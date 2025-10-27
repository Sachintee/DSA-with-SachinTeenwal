---
title: "🔢 Find K Smallest Sum Pairs | GFG Solution 🔍"
keywords🏷️: ["🔢 k smallest pairs", "🔍 min heap", "📍 priority queue", "📈 two pointers", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to Find K Smallest Sum Pairs problem: efficiently find k pairs with smallest sums from two sorted arrays using optimized heap approach. 🚀"
date: 📅 2025-10-27
---

# *300. Find K Smallest Sum Pairs*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/find-k-smallest-sum-pairs/1)

## **🧩 Problem Description**

You are given two integer arrays `arr1[]` and `arr2[]` sorted in ascending order and an integer `k`. Your task is to find `k` pairs with the **smallest sums**, such that one element of each pair belongs to `arr1[]` and the other belongs to `arr2[]`.

Return the list of these `k` pairs, where each pair is represented as `[arr1[i], arr2[j]]`.


## Code(C++)
```cpp
class Solution {
public:
    vector<vector<int>> kSmallestPair(vector<int> &arr1, vector<int> &arr2, int k) {
        vector<vector<int>> res;
        priority_queue<pair<int,pair<int,int>>, vector<pair<int,pair<int,int>>>, greater<>> pq;
        for(int i = 0; i < min((int)arr1.size(), k); i++) pq.push({arr1[i] + arr2[0], {i, 0}});
        while(k-- && !pq.empty()) {
            auto [sum, idx] = pq.top(); pq.pop();
            auto [i, j] = idx;
            res.push_back({arr1[i], arr2[j]});
            if(j + 1 < arr2.size()) pq.push({arr1[i] + arr2[j + 1], {i, j + 1}});
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<ArrayList<Integer>> kSmallestPair(int[] arr1, int[] arr2, int k) {
        ArrayList<ArrayList<Integer>> res = new ArrayList<>();
        PriorityQueue<int[]> pq = new PriorityQueue<>((a, b) -> a[0] - b[0]);
        for(int i = 0; i < Math.min(arr1.length, k); i++) pq.offer(new int[]{arr1[i] + arr2[0], i, 0});
        while(k-- > 0 && !pq.isEmpty()) {
            int[] cur = pq.poll();
            int i = cur[1], j = cur[2];
            ArrayList<Integer> pair = new ArrayList<>();
            pair.add(arr1[i]); pair.add(arr2[j]);
            res.add(pair);
            if(j + 1 < arr2.length) pq.offer(new int[]{arr1[i] + arr2[j + 1], i, j + 1});
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def kSmallestPair(self, arr1, arr2, k):
        res = []
        pq = [(arr1[i] + arr2[0], i, 0) for i in range(min(len(arr1), k))]
        heapq.heapify(pq)
        while k and pq:
            s, i, j = heapq.heappop(pq)
            res.append([arr1[i], arr2[j]])
            if j + 1 < len(arr2): heapq.heappush(pq, (arr1[i] + arr2[j + 1], i, j + 1))
            k -= 1
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
