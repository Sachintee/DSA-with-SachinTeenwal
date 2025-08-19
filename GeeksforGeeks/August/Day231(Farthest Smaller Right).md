---
title: "🔢 Farthest Smaller Right | GFG Solution 🔍"
keywords🏷️: ["🔢 farthest smaller", "🔍 binary search", "📍 suffix array", "📈 preprocessing", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Farthest Smaller Right problem: find the farthest index with smaller element to the right using suffix minimum array and binary search technique. 🚀"
date: 📅 2025-08-19
---

# *231. Farthest Smaller Right*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/farthest-smaller-right/1)

## **🧩 Problem Description**

You are given an array `arr[]`. For each element at index `i` (0-based indexing), find the **farthest index j** to the right (i.e., `j > i`) such that `arr[j] < arr[i]`. If no such index exists for a given position, return `-1` for that index. Return the resulting array of answers.

The goal is to efficiently find the rightmost position where a smaller element exists for each array element.


## Code(C++)
```cpp
class Solution {
public:
    vector<int> farMin(vector<int>& arr) {
        int n = arr.size();
        vector<int> ans(n, -1);
        vector<int> suff(n);
        suff[n-1] = arr[n-1];
        for(int i = n-2; i >= 0; --i) suff[i] = min(arr[i], suff[i+1]);
        for(int i = 0; i < n; ++i) {
            int lo = i+1, hi = n-1, res = -1;
            while(lo <= hi) {
                int mid = lo + (hi-lo)/2;
                if(suff[mid] < arr[i]) {
                    res = mid;
                    lo = mid+1;
                } else {
                    hi = mid-1;
                }
            }
            ans[i] = res;
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public ArrayList<Integer> farMin(int[] arr) {
        int n = arr.length;
        ArrayList<Integer> ans = new ArrayList<>();
        int[] suff = new int[n];
        suff[n-1] = arr[n-1];
        for(int i = n-2; i >= 0; --i) suff[i] = Math.min(arr[i], suff[i+1]);
        for(int i = 0; i < n; ++i) {
            int lo = i+1, hi = n-1, res = -1;
            while(lo <= hi) {
                int mid = lo + (hi-lo)/2;
                if(suff[mid] < arr[i]) {
                    res = mid;
                    lo = mid+1;
                } else {
                    hi = mid-1;
                }
            }
            ans.add(res);
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def farMin(self, arr):
        n = len(arr)
        ans = []
        suff = [0] * n
        suff[n-1] = arr[n-1]
        for i in range(n-2, -1, -1):
            suff[i] = min(arr[i], suff[i+1])
        for i in range(n):
            lo, hi, res = i+1, n-1, -1
            while lo <= hi:
                mid = lo + (hi-lo)//2
                if suff[mid] < arr[i]:
                    res = mid
                    lo = mid+1
                else:
                    hi = mid-1
            ans.append(res)
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
