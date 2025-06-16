---
title: "🏗️ Equalize the Towers | GFG Solution 🎯"
keywords🏷️: ["🏗️ tower equalization", "🔍 binary search", "📈 optimization", "💰 minimum cost", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Equalize the Towers problem: find minimum cost to make all towers same height using binary search optimization. 🚀"
date: 📅 2025-06-16
---

# *167. Equalize the Towers*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/equalize-the-towers2804/1)

## **🧩 Problem Description**

You are given an array `heights[]` representing the heights of towers and another array `cost[]` where each element represents the cost of modifying the height of respective tower.

The goal is to make all towers of same height by either **adding or removing blocks** from each tower. Modifying the height of tower 'i' by 1 unit costs `cost[i]`.

Return the **minimum cost** to equalize the heights of all towers.


## Code(C++)
```cpp
class Solution {
public:
    int minCost(vector<int>& heights, vector<int>& cost) {
        int l = 0, h = *max_element(heights.begin(), heights.end());
        while (l < h) {
            int m = l + (h - l) / 2;
            long long c1 = 0, c2 = 0;
            for (int i = 0; i < heights.size(); ++i) {
                c1 += (long long)abs(heights[i] - m) * cost[i];
                c2 += (long long)abs(heights[i] - m - 1) * cost[i];
            }
            c1 <= c2 ? h = m : l = m + 1;
        }
        long long ans = 0;
        for (int i = 0; i < heights.size(); ++i)
            ans += (long long)abs(heights[i] - l) * cost[i];
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int minCost(int[] heights, int[] cost) {
        int l = 0, h = Arrays.stream(heights).max().getAsInt();
        while (l < h) {
            int m = l + (h - l) / 2;
            long c1 = 0, c2 = 0;
            for (int i = 0; i < heights.length; ++i) {
                c1 += (long)Math.abs(heights[i] - m) * cost[i];
                c2 += (long)Math.abs(heights[i] - m - 1) * cost[i];
            }
            if (c1 <= c2) h = m;
            else l = m + 1;
        }
        long ans = 0;
        for (int i = 0; i < heights.length; ++i)
            ans += (long)Math.abs(heights[i] - l) * cost[i];
        return (int)ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def minCost(self, heights, cost):
        l, h = 0, max(heights)
        while l < h:
            m = l + (h - l) // 2
            c1 = sum(abs(heights[i] - m) * cost[i] for i in range(len(heights)))
            c2 = sum(abs(heights[i] - m - 1) * cost[i] for i in range(len(heights)))
            if c1 <= c2:
                h = m
            else:
                l = m + 1
        return sum(abs(heights[i] - l) * cost[i] for i in range(len(heights)))
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
