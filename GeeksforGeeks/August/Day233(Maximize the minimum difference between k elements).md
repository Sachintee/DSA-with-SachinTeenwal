---
title: "📏 Maximize the Minimum Difference Between K Elements | GFG Solution 🔍"
keywords🏷️: ["📏 maximize minimum", "🔍 binary search", "📍 greedy algorithm", "📈 sorting", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Maximize the Minimum Difference Between K Elements problem: select k elements to maximize minimum absolute difference using binary search and greedy approach. 🚀"
date: 📅 2025-08-21
---

# *233. Maximize the Minimum Difference Between K Elements*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/maximize-the-minimum-difference-between-k-elements/1)

## **🧩 Problem Description**

You are given an array `arr[]` of integers and an integer `k`. Your task is to select **k elements** from the array such that the **minimum absolute difference** between any two of the selected elements is **maximized**. Return this maximum possible minimum difference.

The goal is to strategically choose k elements from the array to ensure that even the closest pair among the selected elements has the largest possible difference.


## Code(C++)
```cpp
class Solution {
public:
    int maxMinDiff(vector<int>& a, int k) {
        sort(a.begin(), a.end());
        int l = 0, r = a.back() - a[0], ans = 0;
        while (l <= r) {
            int m = l + (r - l) / 2;
            int cnt = 1, last = a[0];
            for (int i = 1; i < a.size() && cnt < k; i++)
                if (a[i] - last >= m) cnt++, last = a[i];
            cnt >= k ? ans = m, l = m + 1 : r = m - 1;
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int maxMinDiff(int[] a, int k) {
        Arrays.sort(a);
        int l = 0, r = a[a.length - 1] - a[0], ans = 0;
        while (l <= r) {
            int m = l + (r - l) / 2;
            int cnt = 1, last = a[0];
            for (int i = 1; i < a.length && cnt < k; i++)
                if (a[i] - last >= m) { cnt++; last = a[i]; }
            if (cnt >= k) { ans = m; l = m + 1; } else r = m - 1;
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def maxMinDiff(self, a, k):
        a.sort()
        l, r, ans = 0, a[-1] - a[0], 0
        while l <= r:
            m = (l + r) // 2
            cnt, last = 1, a[0]
            for x in a[1:]:
                if x - last >= m:
                    cnt += 1
                    last = x
                    if cnt == k: break
            if cnt >= k:
                ans, l = m, m + 1
            else:
                r = m - 1
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
