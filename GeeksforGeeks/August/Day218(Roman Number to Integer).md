---
title: "🔢 Roman Number to Integer | GFG Solution 🏛️"
keywords🏷️: ["🔢 roman numerals", "🏛️ string processing", "📊 greedy algorithm", "🔍 pattern matching", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to Roman Number to Integer problem: convert Roman numerals to decimal using greedy pattern matching technique for optimal performance. 🚀"
date: 📅 2025-08-06
---

# *218. Roman Number to Integer*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/roman-number-to-integer3201/1)

## **🧩 Problem Description**

Given a string `s` in Roman number format, your task is to convert it to an integer. Various symbols and their values are given below:

**Roman Numeral Values:**
- I = 1, V = 5, X = 10, L = 50, C = 100, D = 500, M = 1000

**Special Cases (Subtraction Rules):**
- IV = 4, IX = 9, XL = 40, XC = 90, CD = 400, CM = 900

The goal is to parse the Roman numeral string and return its equivalent decimal integer value.


## Code(C++)
```cpp
class Solution {
public:
    int romanToDecimal(string s) {
        int vals[] = {1000,900,500,400,100,90,50,40,10,9,5,4,1};
        string syms[] = {"M","CM","D","CD","C","XC","L","XL","X","IX","V","IV","I"};
        int res = 0, i = 0;
        for (int j = 0; j < 13; j++) {
            while (i + syms[j].length() <= s.length() && s.substr(i, syms[j].length()) == syms[j]) {
                res += vals[j];
                i += syms[j].length();
            }
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public int romanToDecimal(String s) {
        int[] vals = {1000,900,500,400,100,90,50,40,10,9,5,4,1};
        String[] syms = {"M","CM","D","CD","C","XC","L","XL","X","IX","V","IV","I"};
        int res = 0, i = 0;
        for (int j = 0; j < 13; j++) {
            while (i + syms[j].length() <= s.length() && s.substring(i, i + syms[j].length()).equals(syms[j])) {
                res += vals[j];
                i += syms[j].length();
            }
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def romanToDecimal(self, s): 
        vals = [1000,900,500,400,100,90,50,40,10,9,5,4,1]
        syms = ["M","CM","D","CD","C","XC","L","XL","X","IX","V","IV","I"]
        res = i = 0
        for j in range(13):
            while i + len(syms[j]) <= len(s) and s[i:i+len(syms[j])] == syms[j]:
                res += vals[j]
                i += len(syms[j])
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
