---
title: "🏆 Maximum Sum Combination | GFG Solution 🔍"
keywords🏷️: ["🏆 maximum sum", "🔍 priority queue", "📍 heap", "📈 greedy", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Maximum Sum Combination problem: find top k maximum sum pairs from two arrays using priority queue and greedy approach. 🚀"
date: 📅 2025-07-06
---

# *187. Maximum Sum Combination*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/maximum-sum-combination/1)

## **🧩 Problem Description**

You are given two integer arrays `a[]` and `b[]` of equal size. A sum combination is formed by adding one element from `a[]` and one from `b[]`, using each index pair `(i, j)` at most once. Your task is to return the **top k maximum sum combinations**, sorted in non-increasing order.

The goal is to efficiently find the k largest possible sums without generating all n² combinations, which would be inefficient for large arrays.

## Code(C++)
```cpp
class Solution {
public:
    vector<int> topKSumPairs(vector<int>& a, vector<int>& b, int k) {
        int n = a.size();
        sort(a.begin(), a.end(), greater<>());
        sort(b.begin(), b.end(), greater<>());
        priority_queue<tuple<int, int, int>> pq;
        unordered_set<long long> vis;
        pq.emplace(a[0] + b[0], 0, 0);
        vis.insert(0);
        vector<int> res;
        while (res.size() < k) {
            int sum = get<0>(pq.top());
            int i = get<1>(pq.top());
            int j = get<2>(pq.top());
            pq.pop();
            res.push_back(sum);
            if (i + 1 < n && vis.insert((long long)(i + 1) * n + j).second)
                pq.emplace(a[i + 1] + b[j], i + 1, j);
            if (j + 1 < n && vis.insert((long long)i * n + j + 1).second)
                pq.emplace(a[i] + b[j + 1], i, j + 1);
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<Integer> topKSumPairs(int[] a, int[] b, int k) {
        int n = a.length;
        Arrays.sort(a); Arrays.sort(b);
        PriorityQueue<int[]> pq = new PriorityQueue<>((x, y) -> y[0] - x[0]);
        Set<String> vis = new HashSet<>();
        pq.add(new int[]{a[n - 1] + b[n - 1], n - 1, n - 1});
        vis.add((n - 1) + "#" + (n - 1));
        ArrayList<Integer> res = new ArrayList<>();
        while (res.size() < k) {
            int[] top = pq.poll();
            res.add(top[0]);
            int i = top[1], j = top[2];
            if (i > 0 && vis.add((i - 1) + "#" + j))
                pq.add(new int[]{a[i - 1] + b[j], i - 1, j});
            if (j > 0 && vis.add(i + "#" + (j - 1)))
                pq.add(new int[]{a[i] + b[j - 1], i, j - 1});
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def topKSumPairs(self, a, b, k):
        n = len(a)
        a.sort()
        b.sort()
        pq = [(-(a[-1] + b[-1]), n - 1, n - 1)]
        vis = {(n - 1, n - 1)}
        res = []
        while len(res) < k:
            s, i, j = heapq.heappop(pq)
            res.append(-s)
            if i > 0 and (i - 1, j) not in vis:
                vis.add((i - 1, j))
                heapq.heappush(pq, (-(a[i - 1] + b[j]), i - 1, j))
            if j > 0 and (i, j - 1) not in vis:
                vis.add((i, j - 1))
                heapq.heappush(pq, (-(a[i] + b[j - 1]), i, j - 1))
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
