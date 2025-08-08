---
title: "🔢 Longest Prefix Suffix | GFG Solution 🔍"
keywords🏷️: ["🔢 longest prefix suffix", "🔍 KMP algorithm", "📍 pattern matching", "📈 LPS array", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Longest Prefix Suffix problem: find the length of longest proper prefix which is also a suffix using KMP's LPS array construction technique. 🚀"
date: 📅 2025-08-08
---

# *220. Longest Prefix Suffix*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/longest-prefix-suffix2527/1)

## **🧩 Problem Description**

Given a string `s` of lowercase English alphabets, find the length of the **longest proper prefix** which is also a **suffix**.

**Note:** Prefix and suffix can be overlapping but they should not be equal to the entire string.

A proper prefix is a prefix that is not equal to the string itself. Similarly, a proper suffix is a suffix that is not equal to the string itself.


## Code(C++)
```cpp
class Solution {
public:
    int getLPSLength(string &s) {
        int n = s.length(), j = 0;
        vector<int> lps(n, 0);
        for (int i = 1; i < n; ) {
            if (s[i] == s[j]) lps[i++] = ++j;
            else if (j) j = lps[j - 1];
            else i++;
        }
        return lps[n - 1];
    }
};
```

## Code (Java)

```java
class Solution {
    int getLPSLength(String s) {
        int n = s.length(), j = 0;
        int[] lps = new int[n];
        for (int i = 1; i < n; ) {
            if (s.charAt(i) == s.charAt(j)) lps[i++] = ++j;
            else if (j > 0) j = lps[j - 1];
            else i++;
        }
        return lps[n - 1];
    }
}
```

## Code (Python)

```python
class Solution:
    def getLPSLength(self, s):
        n, j, lps = len(s), 0, [0] * len(s)
        i = 1
        while i < n:
            if s[i] == s[j]:
                j += 1
                lps[i] = j
                i += 1
            elif j:
                j = lps[j - 1]
            else:
                i += 1
        return lps[-1]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
