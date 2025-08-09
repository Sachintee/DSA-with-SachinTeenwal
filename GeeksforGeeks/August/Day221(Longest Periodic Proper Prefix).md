---
title: "🔤 Longest Periodic Proper Prefix | GFG Solution 🔍"
keywords🏷️: ["🔤 longest prefix", "🔍 Z-algorithm", "📍 string matching", "📈 prefix function", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Longest Periodic Proper Prefix problem: find the length of longest periodic proper prefix using Z-algorithm technique. 🚀"
date: 📅 2025-08-09
---

# *221. Longest Periodic Proper Prefix*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/longest-periodic-proper-prefix/1)

## **🧩 Problem Description**

Given a string `s`, find the length of the **longest periodic proper prefix** of `s`. If no such prefix exists, return `-1`.

A **periodic proper prefix** is a non-empty prefix of `s` (but not the whole string), such that repeating this prefix enough times produces a string that starts with `s`.


## Code(C++)
```cpp
class Solution {
public:
    int getLongestPrefix(string s) {
        int n = s.size(), l = 0, r = 0, ans = -1;
        vector<int> z(n);
        for (int i = 1; i < n; i++) {
            if (i <= r) z[i] = min(r - i + 1, z[i - l]);
            while (i + z[i] < n && s[z[i]] == s[i + z[i]]) z[i]++;
            if (i + z[i] - 1 > r) l = i, r = i + z[i] - 1;
            if (z[i] == n - i) ans = i;
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    int getLongestPrefix(String s) {
        int n = s.length(), l = 0, r = 0, ans = -1;
        int[] z = new int[n];
        for (int i = 1; i < n; i++) {
            if (i <= r) z[i] = Math.min(r - i + 1, z[i - l]);
            while (i + z[i] < n && s.charAt(z[i]) == s.charAt(i + z[i])) z[i]++;
            if (i + z[i] - 1 > r) { l = i; r = i + z[i] - 1; }
            if (z[i] == n - i) ans = i;
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def getLongestPrefix(self, s):
        n, l, r, ans = len(s), 0, 0, -1
        z = [0] * n
        for i in range(1, n):
            if i <= r:
                z[i] = min(r - i + 1, z[i - l])
            while i + z[i] < n and s[z[i]] == s[i + z[i]]:
                z[i] += 1
            if i + z[i] - 1 > r:
                l, r = i, i + z[i] - 1
            if z[i] == n - i:
                ans = i
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
