---
title: "🍌 Koko Eating Bananas | GFG Solution 🚀"
keywords🏷️: ["🍌 koko bananas", "🔍 binary search", "⏰ minimum speed", "📊 optimization", "📘 GFG", "🏁 competitive programming", "📚 DSA", "🐒 gfg bananas"]
description: "✅ GFG solution to the Koko Eating Bananas problem: find minimum eating speed to finish all banana piles within k hours using binary search. 🚀"
date: 📅 2025-06-13
---

# *164. Koko Eating Bananas*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/koko-eating-bananas/1)

## **🧩 Problem Description**

Koko is given an array `arr[]`, where each element represents a pile of bananas. She has exactly `k` hours to eat all the bananas.

Each hour, Koko can choose one pile and eat up to `s` bananas from it:
- If the pile has at least `s` bananas, she eats exactly `s` bananas
- If the pile has fewer than `s` bananas, she eats the entire pile in that hour
- Koko can only eat from one pile per hour

Your task is to find the **minimum value of s** (bananas per hour) such that Koko can finish all the piles within `k` hours.


## Code(C++)
```cpp
class Solution {
  public:
    int kokoEat(vector<int>& arr, int k) {
        int lo = 1, hi = *max_element(arr.begin(), arr.end());
        
        while (lo < hi) {
            int mid = lo + (hi - lo) / 2;
            int hours = 0;
            for (int pile : arr) {
                hours += (pile + mid - 1) / mid;
            }
            if (hours <= k)
                hi = mid;
            else
                lo = mid + 1;
        }
        return lo;
    }
};
```

## Code (Java)

```java
class Solution {
    public int kokoEat(int[] arr, int k) {
        int lo = 1, hi = 0;
        for (int pile : arr) hi = Math.max(hi, pile);
        
        while (lo < hi) {
            int mid = lo + (hi - lo) / 2;
            int hours = 0;
            for (int pile : arr) {
                hours += (pile + mid - 1) / mid;
            }
            if (hours <= k) hi = mid;
            else lo = mid + 1;
        }
        return lo;
    }
}
```

## Code (Python)

```python
class Solution:
    def kokoEat(self, arr, k):
        lo, hi = 1, max(arr)
        while lo < hi:
            mid = (lo + hi) // 2
            hours = sum((pile + mid - 1) // mid for pile in arr)
            if hours <= k:
                hi = mid
            else:
                lo = mid + 1
        return lo
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
