---
title: "🐜 Last Moment Before All Ants Fall Out | GFG Solution 🚀"
keywords🏷️: ["🐜 ants problem", "🎯 simulation", "📐 physics", "⚡ optimization", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Last Moment Before All Ants Fall Out problem: find when the last ant falls off the plank using optimal physics-based approach. 🚀"
date: 📅 2025-07-24
---

# *205. Last Moment Before All Ants Fall Out*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/last-moment-before-all-ants-fall-out-of-a-plank/1)

## **🧩 Problem Description**

You are given a wooden plank of length `n` units. Some ants are walking on the plank, some are walking left and some are walking right. Each ant moves with speed 1 unit per second.

When two ants moving in opposite directions meet at some point, they change their directions and continue moving again. Assume changing directions does not take any additional time. When an ant reaches one end of the plank at time `t`, it falls out of the plank immediately.

Given an integer `n` and two integer arrays `left[]` and `right[]`, representing the positions of ants moving to the left and right respectively, return the time when the last ant(s) fall out of the plank.


## Code(C++)
```cpp
class Solution {
public:
    int getLastMoment(int n, vector<int>& left, vector<int>& right) {
        int ans = 0;
        for (int x : left) ans = max(ans, x);
        for (int x : right) ans = max(ans, n - x);
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int getLastMoment(int n, int left[], int right[]) {
        int ans = 0;
        for (int x : left) ans = Math.max(ans, x);
        for (int x : right) ans = Math.max(ans, n - x);
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def getLastMoment(self, n, left, right):
        ans = 0
        for x in left: ans = max(ans, x)
        for x in right: ans = max(ans, n - x)
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
