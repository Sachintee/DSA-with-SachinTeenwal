---
title: "🎯 K Closest Elements | GFG Solution 🔍"
keywords🏷️: ["🎯 k closest", "🔍 binary search", "📍 two pointers", "📈 sorted array", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the K Closest Elements problem: find k closest elements to target x in sorted array using binary search and two pointers. 🚀"
date: 📅 2025-06-12
---

# *163. K Closest Elements*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/k-closest-elements3619/1)


## Code(C++)
```cpp
class Solution {
  public:
    vector<int> printKClosest(vector<int> a, int k, int x) {
        int n = a.size(), l = 0, h = n - 1, p = -1;
        while (l <= h) {
            int m = (l + h) / 2;
            if (a[m] < x) p = m, l = m + 1;
            else h = m - 1;
        }
        int i = p, j = p + 1;
        if (j < n && a[j] == x) j++;
        vector<int> r;
        while (i >= 0 && j < n && r.size() < k)
            r.push_back(abs(a[i] - x) < abs(a[j] - x) ? a[i--] : a[j++]);
        while (i >= 0 && r.size() < k) r.push_back(a[i--]);
        while (j < n && r.size() < k) r.push_back(a[j++]);
        return r;
    }
};
```

## Code (Java)

```java
class Solution {
    int[] printKClosest(int[] a, int k, int x) {
        int n = a.length, l = 0, h = n - 1, p = -1;
        while (l <= h) {
            int m = (l + h) / 2;
            if (a[m] < x) { p = m; l = m + 1; }
            else h = m - 1;
        }
        int i = p, j = p + 1;
        if (j < n && a[j] == x) j++;
        int[] r = new int[k]; int idx = 0;
        while (i >= 0 && j < n && idx < k)
            r[idx++] = Math.abs(a[i] - x) < Math.abs(a[j] - x) ? a[i--] : a[j++];
        while (i >= 0 && idx < k) r[idx++] = a[i--];
        while (j < n && idx < k) r[idx++] = a[j++];
        return r;
    }
}
```

## Code (Python)

```python
class Solution:
    def printKClosest(self, a, k, x):
        n, l, h, p = len(a), 0, len(a) - 1, -1
        while l <= h:
            m = (l + h) // 2
            if a[m] < x: p = m; l = m + 1
            else: h = m - 1
        i, j, r = p, p + 1, []
        if j < n and a[j] == x: j += 1
        while i >= 0 and j < n and len(r) < k:
            r.append(a[i] if abs(a[i] - x) < abs(a[j] - x) else a[j])
            if abs(a[i] - x) < abs(a[j] - x): i -= 1
            else: j += 1
        while i >= 0 and len(r) < k: r.append(a[i]); i -= 1
        while j < n and len(r) < k: r.append(a[j]); j += 1
        return r
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
