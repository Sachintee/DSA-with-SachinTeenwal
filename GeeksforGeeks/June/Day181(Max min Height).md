---
title: "🌸 Max Min Height | GFG Solution 💧"
keywords🏷️: ["🌸 max min height", "💧 flower watering", "🔍 binary search", "📈 greedy algorithm", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Max Min Height problem: maximize minimum flower height after k days of watering using binary search and greedy strategy. 🚀"
date: 📅 2025-06-30
---

# *181. Max Min Height*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/max-min-height--170647/1)

## **🧩 Problem Description**

Given a garden with **n flowers** planted in a row, represented by an array `arr[]` where `arr[i]` denotes the height of the ith flower. You will water them for **k days**. In one day you can water **w continuous flowers**. Whenever you water a flower its height increases by **1 unit**. You have to **maximize the minimum height** of all flowers after k days of watering.


## Code(C++)
```cpp
class Solution {
public:
    bool isPossible(vector<int> &arr, int k, int w, int maxHeight) {
        int n = arr.size();
        vector<int> water(n, 0);
        for (int i = 0; i < n; i++) {
            if (i > 0) water[i] = water[i - 1];
            int currHeight = arr[i] + water[i];
            if (i >= w) currHeight -= water[i - w];
            if (currHeight < maxHeight) {
                int add = maxHeight - currHeight;
                water[i] += add;
                k -= add;
                if (k < 0) return false;
            }
        }
        return true;
    }
    
    int maxMinHeight(vector<int> &arr, int k, int w) {
        int n = arr.size();
        int low = arr[0];
        for (int i = 1; i < n; i++) {
            if (arr[i] < low) low = arr[i];
        }
        int high = low + k, ans = low;
        while (low <= high) {
            int mid = low + (high - low) / 2;
            if (isPossible(arr, k, w, mid)) {
                ans = max(ans, mid);
                low = mid + 1;
            } else {
                high = mid - 1;
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    boolean isPossible(int[] arr, int k, int w, int maxHeight) {
        int n = arr.length;
        int[] water = new int[n];
        for (int i = 0; i < n; i++) {
            if (i > 0) water[i] = water[i - 1];
            int currHeight = arr[i] + water[i];
            if (i >= w) currHeight -= water[i - w];
            if (currHeight < maxHeight) {
                int add = maxHeight - currHeight;
                water[i] += add;
                k -= add;
                if (k < 0) return false;
            }
        }
        return true;
    }
    
    public int maxMinHeight(int[] arr, int k, int w) {
        int n = arr.length;
        int low = arr[0];
        for (int i = 1; i < n; i++) {
            if (arr[i] < low) low = arr[i];
        }
        int high = low + k, ans = low;
        while (low <= high) {
            int mid = low + (high - low) / 2;
            if (isPossible(arr, k, w, mid)) {
                ans = Math.max(ans, mid);
                low = mid + 1;
            } else {
                high = mid - 1;
            }
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def isPossible(self, arr, k, w, maxHeight):
        n = len(arr)
        water = [0] * n
        for i in range(n):
            if i > 0:
                water[i] = water[i - 1]
            currHeight = arr[i] + water[i]
            if i >= w:
                currHeight -= water[i - w]
            if currHeight < maxHeight:
                add = maxHeight - currHeight
                water[i] += add
                k -= add
                if k < 0:
                    return False
        return True
    
    def maxMinHeight(self, arr, k, w):
        n = len(arr)
        low = min(arr)
        high = low + k
        ans = low
        while low <= high:
            mid = low + (high - low) // 2
            if self.isPossible(arr, k, w, mid):
                ans = max(ans, mid)
                low = mid + 1
            else:
                high = mid - 1
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
