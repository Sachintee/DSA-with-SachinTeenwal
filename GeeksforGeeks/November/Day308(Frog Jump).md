---
title: "🐸 Frog Jump | GFG Solution 🔍"
keywords🏷️: ["🐸 frog jump", "🔍 dynamic programming", "📍 space optimization", "📈 DP", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Frog Jump problem: find minimum cost for frog to reach last stair by jumping 1 or 2 steps using dynamic programming with space optimization. 🚀"
date: 📅 2025-11-04
---

# *308. Frog Jump*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/geek-jump/1)

## **🧩 Problem Description**

You are given an integer array `height[]` where `height[i]` represents the height of the i-th stair. A frog starts from the first stair and wants to reach the last stair. From any stair i, the frog has two options:
- Jump to the (i+1)th stair
- Jump to the (i+2)th stair

The cost of a jump is the absolute difference in height between the two stairs. Your task is to determine the **minimum total cost** required for the frog to reach the last stair.


## Code(C++)
```cpp
class Solution {
public:
    int minCost(vector<int>& height) {
        int n = height.size();
        if (n == 1) return 0;
        int a = 0, b = abs(height[1] - height[0]);
        for (int i = 2; i < n; i++) {
            int c = min(b + abs(height[i] - height[i - 1]), a + abs(height[i] - height[i - 2]));
            a = b;
            b = c;
        }
        return b;
    }
};
```

## Code (Java)

```java
class Solution {
    int minCost(int[] height) {
        int n = height.length;
        if (n == 1) return 0;
        int a = 0, b = Math.abs(height[1] - height[0]);
        for (int i = 2; i < n; i++) {
            int c = Math.min(b + Math.abs(height[i] - height[i - 1]), 
                            a + Math.abs(height[i] - height[i - 2]));
            a = b;
            b = c;
        }
        return b;
    }
}
```

## Code (Python)

```python
class Solution:
    def minCost(self, height):
        n = len(height)
        if n == 1: return 0
        a, b = 0, abs(height[1] - height[0])
        for i in range(2, n):
            c = min(b + abs(height[i] - height[i - 1]), a + abs(height[i] - height[i - 2]))
            a, b = b, c
        return b
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
