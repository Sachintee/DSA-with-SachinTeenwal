---
title: "🔁 Palindrome SubStrings | GFG Solution 🎯"
keywords🏷️: ["🔁 palindrome substrings", "🎯 center expansion", "📍 two pointers", "🔍 string processing", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Palindrome SubStrings problem: count all palindromic substrings of length ≥ 2 using efficient center expansion technique. 🚀"
date: 📅 2025-08-10
---

# *222. Palindrome SubStrings*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/count-palindrome-sub-strings-of-a-string0652/1)

## **🧩 Problem Description**

You are given a string `s`. Your task is to count all **palindromic sub-strings** present in the string where the length of the palindromic sub-string must be **greater than or equal to 2**.

A substring is palindromic if it reads the same forwards and backwards. The goal is to efficiently count all such valid palindromic substrings.


## Code(C++)
```cpp
class Solution {
public:
    int countPS(string &s) {
        int n = s.size(), ans = 0;
        auto expand = [&](int l, int r) {
            while (l >= 0 && r < n && s[l--] == s[r++]) ans++;
        };
        for (int i = 0; i < n; i++) {
            expand(i - 1, i + 1); 
            expand(i, i + 1);     
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int countPS(String s) {
        int n = s.length(), ans = 0;
        for (int i = 0; i < n; i++) {
            ans += expand(s, i - 1, i + 1); 
            ans += expand(s, i, i + 1);     
        }
        return ans;
    }

    private int expand(String s, int l, int r) {
        int cnt = 0, n = s.length();
        while (l >= 0 && r < n && s.charAt(l--) == s.charAt(r++)) cnt++;
        return cnt;
    }
}

```

## Code (Python)

```python
class Solution:
    def countPS(self, s):
        n, ans = len(s), 0
        def go(l, r):
            nonlocal ans
            while l >= 0 and r < n and s[l] == s[r]:
                ans += 1
                l -= 1
                r += 1
        for i in range(n):
            go(i-1, i+1)
            go(i, i+1)
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
