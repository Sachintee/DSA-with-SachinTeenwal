---
title: "🔍 Search Pattern (Rabin-Karp Algorithm) | GFG Solution 🧠"
keywords🏷️: ["🔍 string matching", "🧪 Rabin-Karp", "🧠 hashing", "📘 GFG", "🔢 pattern search", "💡 substring search", "📚 DSA", "🏁 competitive programming"]
description: "✅ GFG solution for Rabin-Karp based substring search. Fast, efficient pattern matching using rolling hash! 🚀"
date: 📅 2025-06-06
---

# *157. Search Pattern (Rabin-Karp Algorithm)*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/search-pattern-rabin-karp-algorithm--141631/1)


## **🧩 Problem Description**

Given two strings:

* A **text** string in which to search.
* A **pattern** string to find.

Return **all starting positions** (1-based) where the pattern occurs in the text. Use the **Rabin-Karp Algorithm** (rolling hash-based pattern matching).


## Code(C++)
```cpp
class Solution {
  public:
    vector<int> search(string pat, string txt) {
        int d = 256, q = 101, m = pat.length(), n = txt.length();
        int ph = 0, th = 0, h = 1;
        vector<int> res;
        for (int i = 0; i < m - 1; i++) h = (h * d) % q;
        for (int i = 0; i < m; i++) {
            ph = (d * ph + pat[i]) % q;
            th = (d * th + txt[i]) % q;
        }
        for (int i = 0; i <= n - m; i++) {
            if (ph == th) {
                bool match = true;
                for (int j = 0; j < m; j++)
                    if (txt[i + j] != pat[j]) { match = false; break; }
                if (match) res.push_back(i + 1);
            }
            if (i < n - m) {
                th = (d * (th - txt[i] * h) + txt[i + m]) % q;
                if (th < 0) th += q;
            }
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    ArrayList<Integer> search(String pat, String txt) {
        int d = 256, q = 101, m = pat.length(), n = txt.length();
        int ph = 0, th = 0, h = 1;
        ArrayList<Integer> res = new ArrayList<>();
        for (int i = 0; i < m - 1; i++) h = (h * d) % q;
        for (int i = 0; i < m; i++) {
            ph = (d * ph + pat.charAt(i)) % q;
            th = (d * th + txt.charAt(i)) % q;
        }
        for (int i = 0; i <= n - m; i++) {
            if (ph == th) {
                boolean match = true;
                for (int j = 0; j < m; j++) {
                    if (txt.charAt(i + j) != pat.charAt(j)) {
                        match = false;
                        break;
                    }
                }
                if (match) res.add(i + 1);
            }
            if (i < n - m) {
                th = (d * (th - txt.charAt(i) * h) + txt.charAt(i + m)) % q;
                if (th < 0) th += q;
            }
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def search(self, pat, txt):
        d, q, m, n = 256, 101, len(pat), len(txt)
        ph = th = 0; h = 1; res = []
        for i in range(m - 1): h = (h * d) % q
        for i in range(m):
            ph = (d * ph + ord(pat[i])) % q
            th = (d * th + ord(txt[i])) % q
        for i in range(n - m + 1):
            if ph == th and txt[i:i + m] == pat:
                res.append(i + 1)
            if i < n - m:
                th = (d * (th - ord(txt[i]) * h) + ord(txt[i + m])) % q
                if th < 0: th += q
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
