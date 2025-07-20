---
title: "🔢 Count Numbers Containing Specific Digits | GFG Solution 🔍"
keywords🏷️: ["🔢 count numbers", "🔍 combinatorics", "📍 digit counting", "📈 complement counting", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Count Numbers Containing Specific Digits problem: find total n-digit numbers containing at least one digit from given array using complement counting technique. 🚀"
date: 📅 2025-07-20
---

# *201. Count Numbers Containing Specific Digits*

The problem can be found at the following link: 🔗 [Question Link](http://geeksforgeeks.org/problems/count-numbers-containing-specific-digits/1)

## **🧩 Problem Description**

You are given an integer `n` representing the number of digits in a number, and an array `arr[]` containing digits from 0 to 9. Your task is to count how many **n-digit positive integers** can be formed such that **at least one digit** from the array `arr[]` appears in the number.

An n-digit positive integer is a number that has exactly n digits and doesn't start with 0 (except when n=1, where single digit 0 is not considered a positive integer).


## Code(C++)
```cpp

class Solution {
public:
    int countValid(int n, vector<int>& arr) {
        int mask = 0, nonZeroMask = 0;
        for (int d : arr) {
            mask |= (1 << d);
            if (d) nonZeroMask |= (1 << d);
        }
        int forbidden = __builtin_popcount(~mask & 1023);
        int nonZeroForbidden = __builtin_popcount(~nonZeroMask & 1022);
        
        int total = 9, pow = 1;
        for (int i = 1; i < n; i++) {
            pow *= 10;
            total *= 10;
        }
        
        int invalid = n == 1 ? nonZeroForbidden : nonZeroForbidden;
        for (int i = 1; i < n; i++) invalid *= forbidden;
        
        return total - invalid;
    }
};
```

## Code (Java)

```java
class Solution {
    public int countValid(int n, int[] arr) {
        boolean[] allowed = new boolean[10];
        for (int d : arr) allowed[d] = true;
        
        int forbidden = 0, nonZeroForbidden = 0;
        for (int i = 0; i < 10; i++) {
            if (!allowed[i]) {
                forbidden++;
                if (i != 0) nonZeroForbidden++;
            }
        }
        
        long total = 9;
        for (int i = 1; i < n; i++) total *= 10;
        
        long invalid = (n == 1) ? nonZeroForbidden : nonZeroForbidden;
        for (int i = 1; i < n; i++) invalid *= forbidden;
        
        return (int)(total - invalid);
    }
}
```

## Code (Python)

```python
class Solution:
    def countValid(self, n, arr):
        allowed = [False] * 10
        for d in arr:
            allowed[d] = True
        
        forbidden = sum(1 for i in range(10) if not allowed[i])
        non_zero_forbidden = sum(1 for i in range(1, 10) if not allowed[i])
        
        total = 9 * (10 ** (n - 1))
        invalid = non_zero_forbidden * (forbidden ** (n - 1)) if n > 1 else non_zero_forbidden
        
        return total - invalid
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
