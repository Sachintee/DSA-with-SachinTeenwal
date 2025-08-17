---
title: "📏 Sort by Absolute Difference | GFG Solution 🔍"
keywords🏷️: ["📏 sorting", "🔍 absolute difference", "📍 stable sort", "📈 custom comparator", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Sort by Absolute Difference problem: rearrange array elements based on their absolute difference from a target value using stable sorting technique. 🚀"
date: 📅 2025-08-17
---

# *228. Sort by Absolute Difference*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/sort-by-absolute-difference-1587115621/1)

## **🧩 Problem Description**

You are given a number `x` and array `arr[]`. Your task is to rearrange the elements of the array according to the **absolute difference** with `x`, i.e., an element having minimum difference comes first, and so on.

**Note:** If two or more elements are at equal distances arrange them in the same sequence as in the given array.


## Code(C++)
```cpp
class Solution {
public:
    void rearrange(vector<int> &arr, int x) {
        stable_sort(arr.begin(), arr.end(), [x](int a, int b) {
            return abs(a - x) < abs(b - x);
        });
    }
};
```

## Code (Java)

```java
class Solution {
    public void rearrange(int[] arr, int x) {
        Integer[] indices = new Integer[arr.length];
        for (int i = 0; i < arr.length; i++) indices[i] = i;
        Arrays.sort(indices, (a, b) -> Integer.compare(Math.abs(arr[a] - x), Math.abs(arr[b] - x)));
        int[] temp = new int[arr.length];
        for (int i = 0; i < arr.length; i++) temp[i] = arr[indices[i]];
        System.arraycopy(temp, 0, arr, 0, arr.length);
    }
}
```

## Code (Python)

```python
class Solution:
    def rearrange(self, arr, x):
        arr.sort(key=lambda val: abs(val - x))
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
