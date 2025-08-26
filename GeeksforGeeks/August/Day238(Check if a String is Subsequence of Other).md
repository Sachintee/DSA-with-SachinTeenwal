---
title: "🔤 Check if a String is Subsequence of Other | GFG Solution 🔍"
keywords🏷️: ["🔤 string subsequence", "🔍 two pointers", "📈 greedy algorithm", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to check if one string is a subsequence of another using efficient two-pointer technique. Find if s1 is subsequence of s2 optimally. 🚀"
date: 📅 2025-08-26
---

# *238. Check if a String is Subsequence of Other*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/given-two-strings-find-if-first-string-is-a-subsequence-of-second/1)

## **🧩 Problem Description**

Given two strings `s1` and `s2`, you need to check whether `s1` is a **subsequence** of `s2` or not.

**Note:** A subsequence is a sequence that can be derived from another sequence by deleting some elements without changing the order of the remaining elements.


## Code(C++)
```cpp
class Solution {
public:
    bool isSubSeq(string& s1, string& s2) {
        int i = 0;
        for (char c : s2) {
            if (i < s1.size() && s1[i] == c) {
                i++;
            }
        }
        return i == s1.size();
    }
};
```

## Code (Java)

```java
class Solution {
    public boolean isSubSeq(String s1, String s2) {
        int i = 0, n = s1.length(), m = s2.length();
        
        for (int j = 0; j < m && i < n; j++) {
            if (s1.charAt(i) == s2.charAt(j)) {
                i++;
            }
        }
        return i == n;
    }
}
```

## Code (Python)

```python
class Solution:
    def isSubSeq(self, s1, s2):
        i = 0
        for c in s2:
            if i < len(s1) and s1[i] == c:
                i += 1
        return i == len(s1)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
