---
title: "🔢 Powerful Integer | GFG Solution 🔍"
keywords🏷️: ["🔢 powerful integer", "🔍 sweep line", "📍 difference array", "📈 interval overlap", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Powerful Integer problem: find maximum integer appearing in at least k intervals using sweep line technique with difference array. 🚀"
date: 📅 2025-07-30
---


# *212. Powerful Integer*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/powerfull-integer--170647/1)

## **🧩 Problem Description**

You are given a 2D integer array `intervals[][]` of length n, where each `intervals[i] = [start, end]` represents a closed interval (i.e., all integers from start to end, inclusive). You are also given an integer `k`. An integer is called **Powerful** if it appears in at least `k` intervals. Find the **maximum Powerful Integer**.

**Note:** If no integer occurs at least k times return -1.


## Code(C++)
```cpp
class Solution {
public:
    int powerfulInteger(vector<vector<int>>& intervals, int k) {
        map<int, int> events;
        for (auto& i : intervals) {
            events[i[0]]++;
            events[i[1] + 1]--;
        }
        int count = 0, result = -1;
        for (auto& e : events) {
            if (e.second > 0) {
                count += e.second;
                if (count >= k) result = e.first;
            } else {
                if (count >= k) result = e.first - 1;
                count += e.second;
            }
        }
        return result;
    }
};
```

## Code (Java)

```java
class Solution {
    public int powerfulInteger(int[][] intervals, int k) {
        TreeMap<Integer, Integer> events = new TreeMap<>();
        for (int[] i : intervals) {
            events.put(i[0], events.getOrDefault(i[0], 0) + 1);
            events.put(i[1] + 1, events.getOrDefault(i[1] + 1, 0) - 1);
        }
        int count = 0, result = -1;
        for (Map.Entry<Integer, Integer> e : events.entrySet()) {
            if (e.getValue() > 0) {
                count += e.getValue();
                if (count >= k) result = e.getKey();
            } else {
                if (count >= k) result = e.getKey() - 1;
                count += e.getValue();
            }
        }
        return result;
    }
}
```

## Code (Python)

```python
from collections import defaultdict

class Solution:
    def powerfulInteger(self, intervals, k):
        events = defaultdict(int)
        for start, end in intervals:
            events[start] += 1
            events[end + 1] -= 1
        
        count, result = 0, -1
        for pos in sorted(events.keys()):
            if events[pos] > 0:
                count += events[pos]
                if count >= k:
                    result = pos
            else:
                if count >= k:
                    result = pos - 1
                count += events[pos]
        return result
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
