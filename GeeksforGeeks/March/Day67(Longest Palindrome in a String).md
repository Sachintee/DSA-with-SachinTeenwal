---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Dynamic Programming
  - Strings
  - palindrome
---

# 🚀 _Day 67. Longest Palindrome in a String_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/dynamic-programming-gfg-160/problem/longest-palindrome-in-a-string3411)  

## 💡 **Problem Description:**

Given a string `s`, your task is to find the **longest palindromic substring** within `s`.  


## Code(C++)
```cpp
class Solution {
  public:
    string longestPalindrome(string &s) {
        int n = s.size(), start = 0, maxLen = 0;
        for (int i = 0; i < n; i++) {
            for (int l : {i, i + 1}) {
                int j = i;
                while (j >= 0 && l < n && s[j] == s[l]) j--, l++;
                if (l - j - 1 > maxLen) start = j + 1, maxLen = l - j - 1;
            }
        }
        return s.substr(start, maxLen);
    }
};
```

## Code (Java)

```java
class Solution {
    static String longestPalindrome(String s) {
        int n = s.length(), start = 0, maxLen = 0;
        for (int i = 0; i < n; i++)
            for (int l : new int[]{i, i + 1}) {
                int j = i;
                while (j >= 0 && l < n && s.charAt(j) == s.charAt(l)) {
                    j--;
                    l++;
                }
                if (l - j - 1 > maxLen) {
                    start = j + 1;
                    maxLen = l - j - 1;
                }
            }
        return s.substring(start, start + maxLen);
    }
}
```

## Code (Python)

```python
class Solution:
    def longestPalindrome(self, s):
        start, max_len = 0, 0
        for i in range(len(s)):
            for l in [i, i + 1]:
                j = i
                while j >= 0 and l < len(s) and s[j] == s[l]: j, l = j - 1, l + 1
                if l - j - 1 > max_len: start, max_len = j + 1, l - j - 1
        return s[start:start + max_len]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
