---
title: "🔤 Palindrome Sentence | GFG Solution 🔍"
keywords🏷️: ["🔤 palindrome", "🔍 two pointers", "📍 string processing", "📈 case insensitive", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Palindrome Sentence problem: check if a string is palindromic after removing non-alphanumeric characters and converting to lowercase using two pointers technique. 🚀"
date: 📅 2025-08-05
---

# *217. Palindrome Sentence*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/string-palindromic-ignoring-spaces4723/1)

## **🧩 Problem Description**

A palindrome sentence is a sequence of characters, such as word, phrase, or series of symbols that reads the same backward as forward after converting all uppercase letters to lowercase and removing all non-alphanumeric characters (including spaces and punctuation).

Your task is to determine if the given string `s` forms a palindrome sentence according to the above definition.


## Code(C++)
```cpp
class Solution {
public:
    bool isPalinSent(string &s) {
        int l = 0, r = s.size() - 1;
        while (l < r) {
            while (l < r && !isalnum(s[l])) l++;
            while (l < r && !isalnum(s[r])) r--;
            if (tolower(s[l++]) != tolower(s[r--])) return false;
        }
        return true;
    }
};
```

## Code (Java)

```java
class Solution {
    public boolean isPalinSent(String s) {
        int l = 0, r = s.length() - 1;
        while (l < r) {
            while (l < r && !Character.isLetterOrDigit(s.charAt(l))) l++;
            while (l < r && !Character.isLetterOrDigit(s.charAt(r))) r--;
            if (Character.toLowerCase(s.charAt(l++)) != Character.toLowerCase(s.charAt(r--))) return false;
        }
        return true;
    }
}
```

## Code (Python)

```python
class Solution:
    def isPalinSent(self, s):
        l, r = 0, len(s) - 1
        while l < r:
            while l < r and not s[l].isalnum(): l += 1
            while l < r and not s[r].isalnum(): r -= 1
            if s[l].lower() != s[r].lower(): return False
            l, r = l + 1, r - 1
        return True
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
