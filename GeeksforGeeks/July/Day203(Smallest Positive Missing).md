---
title: "🧩 Smallest Positive Missing | GFG Solution 🔍"
keywords🏷️: ["🧩 smallest positive missing", "🔍 index marking", "📍 array manipulation", "📈 cyclic sort", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Smallest Positive Missing Number problem: find the smallest missing positive integer using index marking technique with O(n) time and O(1) space. 🚀"
date: 📅 2025-07-22
---

# *203. Smallest Positive Missing*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/smallest-positive-missing-number-1587115621/1)

## **🧩 Problem Description**

You are given an unsorted array `arr[]` of size `N` that can contain **negative numbers** and **zeros**. Your task is to **find the smallest positive number missing from the array**.

### 📝 Important Notes:

* Positive integers start from `1`.
* Ignore all values ≤ 0 and values greater than the array size while computing the result.
* The missing number must be **positive** and **strictly greater than 0**.


## Code(C++)
```cpp
class Solution {
public:
    int missingNumber(vector<int>& a) {
        int n = a.size();
        for (int i = 0; i < n; i++) if (a[i] <= 0) a[i] = n + 1;
        for (int i = 0; i < n; i++) {
            int x = abs(a[i]);
            if (x <= n) a[x - 1] = -abs(a[x - 1]);
        }
        for (int i = 0; i < n; i++) if (a[i] > 0) return i + 1;
        return n + 1;
    }
};
```

## Code (Java)

```java
class Solution {
    public int missingNumber(int[] a) {
        int n = a.length;
        for (int i = 0; i < n; i++) if (a[i] <= 0) a[i] = n + 1;
        for (int i = 0; i < n; i++) {
            int x = Math.abs(a[i]);
            if (x <= n) a[x - 1] = -Math.abs(a[x - 1]);
        }
        for (int i = 0; i < n; i++) if (a[i] > 0) return i + 1;
        return n + 1;
    }
}
```

## Code (Python)

```python
class Solution:
    def missingNumber(self, a):
        n = len(a)
        for i in range(n):
            if a[i] <= 0: a[i] = n + 1
        for i in range(n):
            x = abs(a[i])
            if x <= n: a[x - 1] = -abs(a[x - 1])
        for i in range(n):
            if a[i] > 0: return i + 1
        return n + 1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
