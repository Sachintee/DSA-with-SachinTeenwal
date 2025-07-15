---
title: "➗ Divisible by 13 | GFG Solution 🔍"
keywords🏷️: ["➗ divisible by 13", "🔍 modular arithmetic", "📍 string processing", "📈 number theory", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to check if a large number (given as string) is divisible by 13 using modular arithmetic properties. 🚀"
date: 📅 2025-07-15
---

# *196. Divisible by 13*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/divisible-by-13/1)

## **🧩 Problem Description**

Given a number represented as a string `s` (which may be very large), check whether it is divisible by 13 or not.

Since the number can be extremely large (up to 10^5 digits), we cannot convert it to integer directly. We need to use modular arithmetic properties to solve this efficiently.


## Code(C++)
```cpp
class Solution {
public:
    bool divby13(string &s) {
        int r = 0;
        for (int i = 0; i < s.length(); ++i) {
            r = (r * 10 + s[i] - '0') % 13;
        }
        return !r;
    }
};
```

## Code (Java)

```java
class Solution {
    public boolean divby13(String s) {
        int r = 0;
        for (int i = 0; i < s.length(); ++i) {
            r = (r * 10 + s.charAt(i) - '0') % 13;
        }
        return r == 0;
    }
}
```

## Code (Python)

```python
class Solution:
    def divby13(self, s):
        r = 0
        for c in s:
            r = (r * 10 + int(c)) % 13
        return r == 0
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
