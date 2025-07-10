---
title: "🔤 Find the Longest String | GFG Solution 🔍"
keywords🏷️: ["🔤 longest string", "🔍 prefix validation", "📍 sorting", "📈 hash set", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Find the Longest String problem: find the longest string where every prefix exists in the array using efficient prefix validation technique. 🚀"
date: 📅 2025-07-10
---

# *191. Find the Longest String*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/find-the-longest-string--170645/1)

## **🧩 Problem Description**

Given an array of strings `words[]`, find the longest string in `words[]` such that every prefix of it is also present in the array `words[]`.

If multiple strings have the same maximum length, return the lexicographically smallest one.


## Code(C++)
```cpp
class Solution {
public:
    string longestString(vector<string>& words) {
        sort(words.begin(), words.end());
        unordered_set<string> st;
        string res = "";
        for (string& w : words) {
            if (w.length() == 1 || st.count(w.substr(0, w.length() - 1))) {
                st.insert(w);
                if (w.length() > res.length()) res = w;
            }
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public String longestString(String[] words) {
        Arrays.sort(words);
        Set<String> st = new HashSet<>();
        String res = "";
        for (String w : words) {
            if (w.length() == 1 || st.contains(w.substring(0, w.length() - 1))) {
                st.add(w);
                if (w.length() > res.length()) {
                    res = w;
                }
            }
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def longestString(self, words):
        words.sort()
        st = set()
        res = ""
        for w in words:
            if len(w) == 1 or w[:-1] in st:
                st.add(w)
                if len(w) > len(res):
                    res = w
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
