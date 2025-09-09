---
title: "🐭 Assign Mice Holes | GFG Solution 🕳️"
keywords🏷️: ["🐭 mice assignment", "🔍 greedy algorithm", "📊 sorting", "📈 optimization", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Assign Mice Holes problem: find optimal assignment to minimize maximum time using greedy approach with sorting. 🚀"
date: 📅 2025-09-09
---

# *252. Assign Mice Holes*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/assign-mice-holes3053/1)

## **🧩 Problem Description**

You are given two arrays `mices[]` and `holes[]` of the same size. The array `mices[]` represents the positions of the mice on a straight line, while the array `holes[]` represents the positions of the holes on the same line. Each hole can accommodate exactly one mouse. 

A mouse can either stay in its current position, move one step to the right, or move one step to the left, and each move takes one minute. The task is to assign each mouse to a distinct hole in such a way that the time taken by the last mouse to reach its hole is minimized.


## Code(C++)
```cpp
class Solution {
public:
    int assignHole(vector<int>& m, vector<int>& h) {
        sort(m.begin(), m.end());
        sort(h.begin(), h.end());
        int r = 0;
        for (int i = 0; i < m.size(); ++i) 
            r = max(r, abs(m[i] - h[i]));
        return r;
    }
};
```

## Code (Java)

```java
class Solution {
    public int assignHole(int[] m, int[] h) {
        Arrays.sort(m);
        Arrays.sort(h);
        int r = 0;
        for (int i = 0; i < m.length; i++)
            r = Math.max(r, Math.abs(m[i] - h[i]));
        return r;
    }
}
```

## Code (Python)

```python
class Solution:
    def assignHole(self, m, h):
        m.sort()
        h.sort()
        return max(abs(a - b) for a, b in zip(m, h))
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
