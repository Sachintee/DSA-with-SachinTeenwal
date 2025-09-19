---
title: "🔧 Min Add to Make Parentheses Valid | GFG Solution 🚀"
keywords🏷️: ["🔧 parentheses validation", "🎯 greedy algorithm", "📊 string processing", "⚡ single pass", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Min Add to Make Parentheses Valid problem: find minimum parentheses to add using greedy single-pass algorithm. 🚀"
date: 📅 2025-09-19
---

# *262. Min Add to Make Parentheses Valid*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/min-add-to-make-parentheses-valid/1)

## **🧩 Problem Description**

You are given a string `s` consisting only of the characters `'('` and `')'`. Your task is to determine the **minimum number of parentheses** (either `'('` or `')'`) that must be inserted at any positions to make the string `s` a **valid parentheses string**.

A parentheses string is considered valid if:
- Every opening parenthesis `'('` has a corresponding closing parenthesis `')'`.
- Every closing parenthesis `')'` has a corresponding opening parenthesis `'('`.
- Parentheses are properly nested.


## Code(C++)
```cpp
class Solution {
public:
    int minParentheses(string& s) {
        int open = 0, close = 0;
        for (char c : s) {
            if (c == '(') open++;
            else if (c == ')') open > 0 ? open-- : close++;
        }
        return open + close;
    }
};
```

## Code (Java)

```java
class Solution {
    public int minParentheses(String s) {
        int open = 0, close = 0;
        for (char c : s.toCharArray()) {
            if (c == '(') open++;
            else if (c == ')') if (open > 0) open--; else close++;
        }
        return open + close;
    }
}
```

## Code (Python)

```python
class Solution:
    def minParentheses(self, s):
        open = close = 0
        for c in s:
            if c == '(':
                open += 1
            elif c == ')':
                if open > 0:
                    open -= 1
                else:
                    close += 1
        return open + close
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
