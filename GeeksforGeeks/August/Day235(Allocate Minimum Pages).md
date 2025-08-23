---
title: "📚 Allocate Minimum Pages | GFG Solution 🔍"
keywords🏷️: ["📚 book allocation", "🔍 binary search", "📊 optimization", "📈 divide and conquer", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Allocate Minimum Pages problem: find optimal book allocation to minimize maximum pages per student using binary search technique. 🚀"
date: 📅 2025-08-23
---

# *235. Allocate Minimum Pages*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/allocate-minimum-number-of-pages0937/1)

## **🧩 Problem Description**

You are given an array `arr[]` of integers, where each element `arr[i]` represents the number of pages in the i-th book. You also have an integer `k` representing the number of students. The task is to allocate books to each student such that:

- Each student receives at least one book.
- Each student is assigned a contiguous sequence of books.
- No book is assigned to more than one student.

The objective is to **minimize the maximum number of pages** assigned to any student. In other words, out of all possible allocations, find the arrangement where the student who receives the most pages still has the smallest possible maximum.

**Note:** If it is not possible to allocate books to all students, return -1.


## Code(C++)
```cpp
class Solution {
public:
    int findPages(vector<int> &arr, int k) {
        if (k > arr.size()) return -1;
        int l = *max_element(arr.begin(), arr.end());
        int r = accumulate(arr.begin(), arr.end(), 0);
        while (l < r) {
            int m = l + (r - l) / 2;
            int s = 1, p = 0;
            for (int x : arr) {
                if (p + x > m) { s++; p = x; } 
                else p += x;
            }
            s <= k ? r = m : l = m + 1;
        }
        return l;
    }
};
```

## Code (Java)

```java
class Solution {
    public int findPages(int[] arr, int k) {
        if (k > arr.length) return -1;
        int l = arr[0], r = 0;
        for (int x : arr) {
            l = Math.max(l, x);
            r += x;
        }
        while (l < r) {
            int m = l + (r - l) / 2;
            int s = 1, p = 0;
            for (int x : arr) {
                if (p + x > m) { s++; p = x; }
                else p += x;
            }
            if (s <= k) r = m;
            else l = m + 1;
        }
        return l;
    }
}
```

## Code (Python)

```python
class Solution:
    def findPages(self, arr, k):
        if k > len(arr): return -1
        l, r = max(arr), sum(arr)
        while l < r:
            m = (l + r) // 2
            s, p = 1, 0
            for x in arr:
                if p + x > m: s, p = s + 1, x
                else: p += x
            r, l = (m, l) if s <= k else (r, m + 1)
        return l
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
