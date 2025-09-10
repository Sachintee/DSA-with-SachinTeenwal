---
title: "🔢 Largest Number in One Swap | GFG Solution 🔍"
keywords🏷️: ["🔢 largest number", "🔄 string swap", "📍 greedy algorithm", "📈 optimization", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Largest Number in One Swap problem: find lexicographically largest string by swapping at most one pair of characters using greedy approach. 🚀"
date: 📅 2025-09-10
---

# *253. Largest Number in One Swap*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/largest-number-in-one-swap1520/1)

## **🧩 Problem Description**

Given a string `s`, return the **lexicographically largest string** that can be obtained by swapping **at most one pair** of characters in `s`.

The goal is to maximize the lexicographic value of the string with a single swap operation. If no beneficial swap exists, return the original string.


## Code(C++)
```cpp
class Solution {
public:
    string largestSwap(string &s) {
        int n = s.size(), l = -1, r = -1, maxIdx = n - 1;
        for (int i = n - 2; i >= 0; i--) {
            if (s[i] > s[maxIdx]) maxIdx = i;
            else if (s[i] < s[maxIdx]) l = i, r = maxIdx;
        }
        if (l != -1) swap(s[l], s[r]);
        return s;
    }
};
```

## Code (Java)

```java
class Solution {
    public String largestSwap(String s) {
        char[] a = s.toCharArray();
        int n = a.length, l = -1, r = -1, maxIdx = n - 1;
        for (int i = n - 2; i >= 0; i--) {
            if (a[i] > a[maxIdx]) maxIdx = i;
            else if (a[i] < a[maxIdx]) { l = i; r = maxIdx; }
        }
        if (l != -1) { char t = a[l]; a[l] = a[r]; a[r] = t; }
        return new String(a);
    }
}
```

## Code (Python3)

```python
class Solution:
    def largestSwap(self, s):
        s = list(s)
        n, l, r, maxIdx = len(s), -1, -1, len(s) - 1
        for i in range(n - 2, -1, -1):
            if s[i] > s[maxIdx]: maxIdx = i
            elif s[i] < s[maxIdx]: l, r = i, maxIdx
        if l != -1: s[l], s[r] = s[r], s[l]
        return ''.join(s)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
