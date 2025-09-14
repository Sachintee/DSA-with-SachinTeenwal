---
title: "⛽ Gas Station | GFG Solution 🚗"
keywords🏷️: ["⛽ gas station", "🔄 circular tour", "📍 greedy algorithm", "📈 optimization", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Gas Station problem: find the starting station to complete a circular tour using greedy approach with optimal time and space complexity. 🚀"
date: 📅 2025-09-14
---

# *257. Gas Station*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/circular-tour-1587115620/1)

## **🧩 Problem Description**

You are given two integer arrays `gas[]` and `cost[]` representing n gas stations along a circular tour. At station `i`, you can fill `gas[i]` units of gas and need `cost[i]` units to travel to the next station `(i+1)`. Starting with an empty tank, find the index of the starting station that allows you to complete the entire circular tour without running out of gas. Return `-1` if no such starting station exists.

**Note:** If a solution exists, it is guaranteed to be unique.


## Code(C++)
```cpp
class Solution {
  public:
    int startStation(vector<int>& gas, vector<int>& cost) {
        int total = 0, curr = 0, start = 0;
        for (int i = 0; i < gas.size(); i++) {
            int diff = gas[i] - cost[i];
            total += diff;
            curr += diff;
            if (curr < 0) start = i + 1, curr = 0;
        }
        return total >= 0 ? start : -1;
    }
};
```

## Code (Java)

```java
class Solution {
    public int startStation(int[] gas, int[] cost) {
        int total = 0, curr = 0, start = 0;
        for (int i = 0; i < gas.length; i++) {
            int diff = gas[i] - cost[i];
            total += diff;
            curr += diff;
            if (curr < 0) { start = i + 1; curr = 0; }
        }
        return total >= 0 ? start : -1;
    }
}
```

## Code (Python)

```python
class Solution:
    def startStation(self, gas, cost):
        total = curr = start = 0
        for i in range(len(gas)):
            diff = gas[i] - cost[i]
            total += diff
            curr += diff
            if curr < 0: start, curr = i + 1, 0
        return start if total >= 0 else -1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
