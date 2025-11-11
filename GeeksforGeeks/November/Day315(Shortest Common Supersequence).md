---
title: "🔤 Shortest Common Supersequence | GFG Solution 📏"
keywords🏷️: ["🔤 supersequence", "📏 dynamic programming", "🔍 LCS", "📊 string algorithms", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Shortest Common Supersequence problem: find the length of smallest string containing both input strings as subsequences using dynamic programming. 🚀"
date: 📅 2025-11-11
---

# *315. Shortest Common Supersequence*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/shortest-common-supersequence0322/1)

## **🧩 Problem Description**

Given two strings `s1` and `s2`, find the length of the **smallest string** which has both `s1` and `s2` as its subsequences.

A supersequence is a sequence that contains both strings as subsequences. The goal is to find the minimum length of such a supersequence where characters from both strings can be found in order (not necessarily contiguous).

**Note:** `s1` and `s2` can have both uppercase and lowercase English letters.


## Code(C++)
```cpp
class Solution {
public:
    int minSuperSeq(string &s1, string &s2) {
        int m = s1.size(), n = s2.size();
        vector<int> prev(n + 1), curr(n + 1);
        for (int j = 0; j <= n; j++) prev[j] = j;
        for (int i = 1; i <= m; i++) {
            curr[0] = i;
            for (int j = 1; j <= n; j++) {
                curr[j] = (s1[i - 1] == s2[j - 1]) ? 1 + prev[j - 1] : 
                          1 + min(prev[j], curr[j - 1]);
            }
            prev = curr;
        }
        return prev[n];
    }
};
```

## Code (Java)

```java
class Solution {
    public static int minSuperSeq(String s1, String s2) {
        int m = s1.length(), n = s2.length();
        int[] prev = new int[n + 1], curr = new int[n + 1];
        for (int j = 0; j <= n; j++) prev[j] = j;
        for (int i = 1; i <= m; i++) {
            curr[0] = i;
            for (int j = 1; j <= n; j++) {
                curr[j] = (s1.charAt(i - 1) == s2.charAt(j - 1)) ? 1 + prev[j - 1] : 
                          1 + Math.min(prev[j], curr[j - 1]);
            }
            prev = curr.clone();
        }
        return prev[n];
    }
}
```

## Code (Python)

```python
class Solution:
    def minSuperSeq(self, s1, s2):
        m, n = len(s1), len(s2)
        prev, curr = [0] * (n + 1), [0] * (n + 1)
        for j in range(n + 1): prev[j] = j
        for i in range(1, m + 1):
            curr[0] = i
            for j in range(1, n + 1):
                curr[j] = 1 + prev[j - 1] if s1[i - 1] == s2[j - 1] else 1 + min(prev[j], curr[j - 1])
            prev = curr[:]
        return prev[n]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
