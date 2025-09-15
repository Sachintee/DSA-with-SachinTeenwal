---
title: "🔤 String Stack | GFG Solution 🔍"
keywords🏷️: ["🔤 string stack", "🔍 two pointers", "📍 greedy", "📈 string matching", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the String Stack problem: determine if target string can be constructed from pattern using append/delete operations with optimal two-pointer approach. 🚀"
date: 📅 2025-09-15
---

# *258. String Stack*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/string-stack--165812/1)

## **🧩 Problem Description**

You are given two strings `pat` and `tar` consisting of lowercase English characters. You can construct a new string `s` by performing any one of the following operations for each character in `pat`:

1. **Append** the character `pat[i]` to the string `s`.
2. **Delete** the last character of `s` (if `s` is empty do nothing).

After performing operations on every character of `pat` exactly once, your goal is to determine if it is possible to make the string `s` equal to string `tar`.


## Code(C++)
```cpp
class Solution {
public:
    bool stringStack(string &pat, string &tar) {
        int i = pat.length() - 1, j = tar.length() - 1;
        while (i >= 0 && j >= 0) {
            if (pat[i] == tar[j]) {
                i--; j--;
            } else {
                i -= 2;
            }
        }
        return j < 0;
    }
};
```

## Code (Java)

```java
class Solution {
    public boolean stringStack(String pat, String tar) {
        int i = pat.length() - 1, j = tar.length() - 1;
        while (i >= 0 && j >= 0) {
            if (pat.charAt(i) == tar.charAt(j)) {
                i--; j--;
            } else {
                i -= 2;
            }
        }
        return j < 0;
    }
}
```

## Code (Python)

```python
class Solution:
    def stringStack(self, pat, tar):
        i, j = len(pat) - 1, len(tar) - 1
        while i >= 0 and j >= 0:
            if pat[i] == tar[j]:
                i -= 1
                j -= 1
            else:
                i -= 2
        return j < 0
```

#code

## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
