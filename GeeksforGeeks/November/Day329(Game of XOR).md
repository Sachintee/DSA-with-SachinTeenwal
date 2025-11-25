---
title: "🎮 Game of XOR | GFG Solution 🔍"
keywords🏷️: ["🎮 game of xor", "🔢 bitwise xor", "📊 subarray contribution", "🧮 mathematical optimization", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Game of XOR problem: compute the bitwise XOR of all subarray XORs using mathematical contribution analysis and parity optimization. 🚀"
date: 📅 2025-11-25
---

# *329. Game of XOR*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/game-of-xor1541/1)

## **🧩 Problem Description**

You are given an integer array `arr[]`. The value of a subarray is defined as the **bitwise XOR of all elements** in that subarray.

Your task is to compute the **bitwise XOR of the values of all possible subarrays** of `arr[]`.


## Code(C++)
```cpp
class Solution {
public:
    int subarrayXor(vector<int>& arr) {
        int xor_sum = 0;
        int n = arr.size();
        for (int i = 0; i < n; i++) {
            if (((i + 1) * (n - i)) & 1) xor_sum ^= arr[i];
        }
        return xor_sum;
    }
};
```

## Code (Java)

```java

```

## Code (Python)

```python

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
