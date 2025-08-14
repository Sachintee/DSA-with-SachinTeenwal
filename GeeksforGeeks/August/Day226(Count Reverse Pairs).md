---
title: "🔢 Count Reverse Pairs | GFG Solution 🔍"
keywords🏷️: ["🔢 reverse pairs", "🔍 merge sort", "📍 divide conquer", "📈 inversion count", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Count Reverse Pairs problem: efficiently count pairs (i,j) where arr[i] > 2*arr[j] using modified merge sort technique. 🚀"
date: 📅 2025-08-14
---

# *226. Count Reverse Pairs*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/count-reverse-pairs/1)

## **🧩 Problem Description**

You are given an array `arr[]` of positive integers. Your task is to find the count of **reverse pairs**. A pair of indices `(i, j)` is said to be a reverse pair if both the following conditions are met:

- `0 ≤ i < j < arr.size()`
- `arr[i] > 2 * arr[j]`

The goal is to efficiently count all such pairs in the given array.


## Code(C++)
```cpp
class Solution {
public:
    int countRevPairs(vector<int>& arr) {
        return mergeSort(arr, 0, arr.size() - 1);
    }
private:
    int mergeSort(vector<int>& arr, int l, int r) {
        if (l >= r) return 0;
        int m = l + (r - l) / 2;
        return mergeSort(arr, l, m) + mergeSort(arr, m + 1, r) + merge(arr, l, m, r);
    }
    int merge(vector<int>& arr, int l, int m, int r) {
        int cnt = 0, j = m + 1;
        for (int i = l; i <= m; i++) {
            while (j <= r && arr[i] > 2LL * arr[j]) j++;
            cnt += j - m - 1;
        }
        vector<int> temp(r - l + 1);
        int i = l, k = 0;
        j = m + 1;
        while (i <= m && j <= r) temp[k++] = arr[i] <= arr[j] ? arr[i++] : arr[j++];
        while (i <= m) temp[k++] = arr[i++];
        while (j <= r) temp[k++] = arr[j++];
        for (i = l; i <= r; i++) arr[i] = temp[i - l];
        return cnt;
    }
};
```

## Code (Java)

```java
class Solution {
    public int countRevPairs(int[] arr) {
        return mergeSort(arr, 0, arr.length - 1);
    }
    private int mergeSort(int[] arr, int l, int r) {
        if (l >= r) return 0;
        int m = l + (r - l) / 2;
        return mergeSort(arr, l, m) + mergeSort(arr, m + 1, r) + merge(arr, l, m, r);
    }
    private int merge(int[] arr, int l, int m, int r) {
        int cnt = 0, j = m + 1;
        for (int i = l; i <= m; i++) {
            while (j <= r && arr[i] > 2L * arr[j]) j++;
            cnt += j - m - 1;
        }
        int[] temp = new int[r - l + 1];
        int i = l, k = 0;
        j = m + 1;
        while (i <= m && j <= r) temp[k++] = arr[i] <= arr[j] ? arr[i++] : arr[j++];
        while (i <= m) temp[k++] = arr[i++];
        while (j <= r) temp[k++] = arr[j++];
        System.arraycopy(temp, 0, arr, l, temp.length);
        return cnt;
    }
}
```

## Code (Python)

```python
class Solution:
    def countRevPairs(self, arr):
        def mergeSort(l, r):
            if l >= r: return 0
            m = (l + r) // 2
            return mergeSort(l, m) + mergeSort(m + 1, r) + merge(l, m, r)
        
        def merge(l, m, r):
            cnt = j = 0
            for i in range(l, m + 1):
                while m + 1 + j <= r and arr[i] > 2 * arr[m + 1 + j]: j += 1
                cnt += j
            arr[l:r+1] = sorted(arr[l:r+1])
            return cnt
        
        return mergeSort(0, len(arr) - 1)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
