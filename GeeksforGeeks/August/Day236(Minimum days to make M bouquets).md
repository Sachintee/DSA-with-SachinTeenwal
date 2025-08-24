---
title: "🌸 Minimum Days to Make M Bouquets | GFG Solution 🔍"
keywords🏷️: ["🌸 minimum days", "🔍 binary search", "📈 greedy algorithm", "🌺 bouquets", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Minimum Days to Make M Bouquets problem: find minimum days required to create m bouquets using binary search optimization technique. 🚀"
date: 📅 2025-08-24
---

# *236. Minimum Days to Make M Bouquets*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/minimum-days-to-make-m-bouquets/1)

## **🧩 Problem Description**

You have a row of flowers, where each flower blooms after a specific day. The array `arr[]` represents the blooming schedule: `arr[i]` is the day the flower at position `i` will bloom. To create a bouquet, you need to collect **k adjacent bloomed flowers**. Each flower can only be used in one bouquet.

Your goal is to find the **minimum number of days** required to make exactly **m bouquets**. If it is not possible to make m bouquets with the given arrangement, return **-1**.


## Code(C++)
```cpp
class Solution {
public:
    int minDaysBloom(vector<int>& arr, int k, int m) {
        if ((long long)k * m > arr.size()) return -1;
        int l = *min_element(arr.begin(), arr.end());
        int r = *max_element(arr.begin(), arr.end());
        while (l < r) {
            int mid = l + (r - l) / 2;
            int flowers = 0, bouquets = 0;
            for (int bloom : arr) {
                if (bloom <= mid) {
                    if (++flowers == k) {
                        bouquets++;
                        flowers = 0;
                    }
                } else flowers = 0;
            }
            if (bouquets >= m) r = mid;
            else l = mid + 1;
        }
        return l;
    }
};
```

## Code (Java)

```java
class Solution {
    public int minDaysBloom(int[] arr, int k, int m) {
        if ((long) k * m > arr.length) return -1;
        int l = Arrays.stream(arr).min().getAsInt();
        int r = Arrays.stream(arr).max().getAsInt();
        while (l < r) {
            int mid = l + (r - l) / 2;
            int flowers = 0, bouquets = 0;
            for (int bloom : arr) {
                if (bloom <= mid) {
                    if (++flowers == k) {
                        bouquets++;
                        flowers = 0;
                    }
                } else flowers = 0;
            }
            if (bouquets >= m) r = mid;
            else l = mid + 1;
        }
        return l;
    }
}
```

## Code (Python)

```python
class Solution:
    def minDaysBloom(self, arr, k, m):
        if k * m > len(arr): return -1
        l, r = min(arr), max(arr)
        while l < r:
            mid = (l + r) // 2
            flowers = bouquets = 0
            for bloom in arr:
                if bloom <= mid:
                    flowers += 1
                    if flowers == k:
                        bouquets += 1
                        flowers = 0
                else:
                    flowers = 0
            if bouquets >= m:
                r = mid
            else:
                l = mid + 1
        return l
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
