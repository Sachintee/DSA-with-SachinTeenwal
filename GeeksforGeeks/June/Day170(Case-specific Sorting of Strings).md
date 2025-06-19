---
title: "🔤 Case-specific Sorting of Strings | GFG Solution 🔍"
keywords🏷️: ["🔤 case sorting", "🔠 uppercase lowercase", "🔍 frequency counting", "📍 in-place sorting", "📈 string processing", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Case-specific Sorting of Strings problem: sort uppercase and lowercase characters separately while maintaining their original positions. 🚀"
date: 📅 2025-06-19
---

# *170. Case-specific Sorting of Strings*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/case-specific-sorting-of-strings4845/1)

## **🧩 Problem Description**

Given a string `s` consisting of only uppercase and lowercase characters. The task is to **sort uppercase and lowercase letters separately** such that if the ith place in the original string had an **Uppercase character** then it should not have a **lowercase character** after being sorted and **vice versa**.

An element maintains its case but gets sorted within its case group while preserving the original case pattern of the string.


## Code(C++)
```cpp
class Solution {
public:
    string caseSort(string &s) {
        int l[26] = {0}, u[26] = {0};
        for (char c : s) (c & 32) ? l[c - 97]++ : u[c - 65]++;
        int i = 0, j = 0;
        for (char &c : s) {
            if (c & 32) {
                while (!l[i]) i++;
                c = i + 97;
                l[i]--;
            } else {
                while (!u[j]) j++;
                c = j + 65;
                u[j]--;
            }
        }
        return s;
    }
};
```

## Code (Java)

```java
class Solution {
    public static String caseSort(String s) {
        int[] l = new int[26], u = new int[26];
        char[] c = s.toCharArray();
        for (char ch : c) {
            if (ch >= 'a') l[ch - 97]++;
            else u[ch - 65]++;
        }
        int i = 0, j = 0;
        for (int k = 0; k < c.length; k++) {
            if (c[k] >= 'a') {
                while (l[i] == 0) i++;
                c[k] = (char)(i + 97);
                l[i]--;
            } else {
                while (u[j] == 0) j++;
                c[k] = (char)(j + 65);
                u[j]--;
            }
        }
        return new String(c);
    }
}
```

## Code (Python)

```python
class Solution:
    def caseSort(self, s):
        l, u = [0] * 26, [0] * 26
        for c in s:
            if c.islower():
                l[ord(c) - 97] += 1
            else:
                u[ord(c) - 65] += 1
        r, i, j = list(s), 0, 0
        for k in range(len(s)):
            if s[k].islower():
                while l[i] == 0:
                    i += 1
                r[k] = chr(i + 97)
                l[i] -= 1
            else:
                while u[j] == 0:
                    j += 1
                r[k] = chr(j + 65)
                u[j] -= 1
        return ''.join(r)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
