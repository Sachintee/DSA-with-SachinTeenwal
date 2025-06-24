---
title: "🦁 Lexicographically Largest String After K Deletions | GFG Solution 🔍"
keywords🏷️: ["🦁 lexicographically largest string", "🧹 remove k characters", "🧠 greedy approach", "📘 GFG", "📚 string problems", "🛠️ monotonic stack"]
description: "✅ GFG solution to the Lexicographically Largest String After K Deletions problem: remove exactly k characters to get the largest possible string using greedy approach. 🚀"
date: 📅 2025-06-24
---

# *175. Lexicographically Largest String After K Deletions*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/lexicographically-largest-string-after-deleting-k-characters/1)

## **🧩 Problem Description**

Given a string `s` consisting of lowercase English letters and an integer `k`, your task is to remove exactly **k characters** from the string. The resulting string must be the **largest possible in lexicographical order**, while maintaining the **relative order** of the remaining characters.


## Code(C++)
```cpp
class Solution {
public:
    string maxSubseq(string &s, int k) {
        int n = s.length(), toRemove = k;
        string res;
        for (char c : s) {
            while (!res.empty() && toRemove && res.back() < c) {
                res.pop_back();
                toRemove--;
            }
            res += c;
        }
        res.resize(n - k);
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public static String maxSubseq(String s, int k) {
        int n = s.length(), toRemove = k;
        StringBuilder res = new StringBuilder();
        for (int i = 0; i < n; i++) {
            while (toRemove > 0 && res.length() > 0 && res.charAt(res.length() - 1) < s.charAt(i)) {
                res.deleteCharAt(res.length() - 1);
                toRemove--;
            }
            res.append(s.charAt(i));
        }
        res.setLength(n - k);
        return res.toString();
    }
}
```

## Code (Python)

```python
class Solution:
    def maxSubseq(self, s, k):
        n, toRemove, res = len(s), k, []
        for c in s:
            while res and toRemove and res[-1] < c:
                res.pop()
                toRemove -= 1
            res.append(c)
        return ''.join(res[:n - k])
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
