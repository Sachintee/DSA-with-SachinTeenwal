---
title: "🔢 Counting Elements in Two Arrays | GFG Solution 📊"
keywords🏷️: ["🔢 count elements", "📊 frequency array", "🔍 binary search", "📈 prefix sum", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to count elements in array b that are less than or equal to each element in array a using frequency array and prefix sum technique. 🚀"
date: 📅 2025-06-28
---

# *179. Counting Elements in Two Arrays*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/counting-elements-in-two-arrays/1)

## **🧩 Problem Description**

You are given two **unsorted arrays** `a[]` and `b[]`. Both arrays may contain **duplicate elements**. For each element in `a[]`, your task is to count how many elements in `b[]` are **less than or equal** to that element.


## Code(C++)
```cpp
class Solution {
public:
    vector<int> countLessEq(vector<int>& a, vector<int>& b) {
        int n = a.size(), m = b.size(), mx = *max_element(b.begin(), b.end());
        vector<int> res(n), cnt(mx + 1);
        for (int x : b) cnt[x]++;
        for (int i = 1; i <= mx; i++) cnt[i] += cnt[i - 1];
        for (int i = 0; i < n; i++) res[i] = cnt[min(a[i], mx)];
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public static ArrayList<Integer> countLessEq(int[] a, int[] b) {
        int max = 0;
        for (int x : b) max = Math.max(max, x);
        int[] cnt = new int[max + 1];
        for (int x : b) cnt[x]++;
        for (int i = 1; i <= max; i++) cnt[i] += cnt[i - 1];
        ArrayList<Integer> res = new ArrayList<>();
        for (int x : a) res.add(cnt[Math.min(x, max)]);
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def countLessEq(self, a, b):
        if not b: return [0]*len(a)
        m = max(b)
        cnt = [0]*(m+1)
        for x in b: cnt[x] += 1
        for i in range(1, m+1): cnt[i] += cnt[i-1]
        return [cnt[min(x, m)] for x in a]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
