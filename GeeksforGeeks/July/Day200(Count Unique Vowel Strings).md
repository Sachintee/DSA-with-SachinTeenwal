---
title: "🔤 Count Unique Vowel Strings | GFG Solution 🎯"
keywords🏷️: ["🔤 vowel strings", "🧮 combinatorics", "📊 frequency counting", "🔄 permutations", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to Count Unique Vowel Strings problem: calculate total distinct strings by selecting vowels and forming permutations using combinatorial mathematics. 🚀"
date: 📅 2025-07-19
---

# *200. Count Unique Vowel Strings*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/count-unique-vowel-strings/1)

## **🧩 Problem Description**

You are given a lowercase string `s`, determine the total number of distinct strings that can be formed using the following rules:

1. **Identify** all unique vowels (a, e, i, o, u) present in the string.
2. **Select** exactly one occurrence of each distinct vowel from `s`. If a vowel appears multiple times, each occurrence represents a unique selection choice.
3. **Generate** all possible permutations of the selected vowels. Each unique arrangement counts as a distinct string.

Return the total number of such distinct strings.


## Code(C++)
```cpp
class Solution {
public:
    int vowelCount(string& s) {
        int freq[26] = {}, cnt = 0, mul = 1;
        for (char c : s) if (strchr("aeiou", c)) freq[c - 'a']++;
        for (int v : {0, 4, 8, 14, 20}) if (freq[v]) mul *= freq[v], cnt++;
        return cnt ? mul * tgamma(cnt + 1) : 0;
    }
};
```

## Code (Java)

```java
class Solution {
    public int vowelCount(String s) {
        int[] f = new int[5];
        for (char c : s.toCharArray())
            if ("aeiou".indexOf(c) >= 0) f["aeiou".indexOf(c)]++;
        int cnt = 0, prod = 1;
        for (int x : f) if (x > 0) { prod *= x; cnt++; }
        for (int i = 2; i <= cnt; i++) prod *= i;
        return cnt == 0 ? 0 : prod;
    }
}
```

## Code (Python)

```python
from math import prod, factorial
from collections import Counter
class Solution:
    def vowelCount(self, s):
        freq = Counter(c for c in s if c in 'aeiou')
        vals = list(freq.values())
        return prod(vals) * factorial(len(vals)) if vals else 0
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
