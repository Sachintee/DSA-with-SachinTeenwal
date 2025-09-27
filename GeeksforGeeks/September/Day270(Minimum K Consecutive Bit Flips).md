---
title: "🔢 Minimum K Consecutive Bit Flips | GFG Solution 🔍"
keywords🏷️: ["🔢 bit flips", "🔍 greedy algorithm", "📍 sliding window", "📈 array manipulation", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Minimum K Consecutive Bit Flips problem: find minimum operations to convert all 0's to 1's using greedy approach with in-place marking. 🚀"
date: 📅 2025-09-27
---

# *270. Minimum K Consecutive Bit Flips*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/minimum-number-of-k-consecutive-bit-flips--171650/1)

## **🧩 Problem Description**

You are given a binary array `arr[]` (containing only 0's and 1's) and an integer `k`. In one operation, you can select a contiguous subarray of length `k` and flip all its bits (i.e., change every 0 to 1 and every 1 to 0).

Your task is to find the **minimum number** of such operations required to make the entire array consist of only 1's. If it is not possible, return -1.


## Code(C++)
```cpp
class Solution {
public:
    int kBitFlips(vector<int>& a, int k) {
        int n = a.size(), flips = 0, flip = 0;
        for (int i = 0; i < n; i++) {
            if (i >= k && a[i - k] > 1) flip ^= 1;
            if ((a[i] ^ flip) == 0) {
                if (i + k > n) return -1;
                a[i] = 2;
                flip ^= 1;
                flips++;
            }
        }
        return flips;
    }
};
```

## Code (Java)

```java
class Solution {
    public int kBitFlips(int[] a, int k) {
        int n = a.length, flips = 0, flip = 0;
        for (int i = 0; i < n; i++) {
            if (i >= k && a[i - k] > 1) flip ^= 1;
            if ((a[i] ^ flip) == 0) {
                if (i + k > n) return -1;
                a[i] = 2;
                flip ^= 1;
                flips++;
            }
        }
        return flips;
    }
}
```

## Code (Python)

```python
class Solution:
    def kBitFlips(self, a, k):
        n, flips, flip = len(a), 0, 0
        for i in range(n):
            if i >= k and a[i - k] > 1: flip ^= 1
            if (a[i] ^ flip) == 0:
                if i + k > n: return -1
                a[i] = 2
                flip ^= 1
                flips += 1
        return flips
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
