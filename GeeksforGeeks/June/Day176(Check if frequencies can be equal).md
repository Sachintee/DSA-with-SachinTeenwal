---
title: "🧪 Check if Frequencies Can Be Equal | GFG Solution 🔍"
keywords🏷️: ["🧪 frequency check", "🧮 character frequency", "🔠 string", "🗑️ remove one char", "📈 hash map", "🏁 competitive programming", "📘 GFG", "📚 DSA", "🧠 hashing"]
description: "✅ GFG solution to Check if Frequencies Can Be Equal problem: determine if removing at most one character makes all character frequencies equal. 🚀"
date: 📅 2025-06-25
---

# *176. Check if Frequencies Can Be Equal*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/check-frequencies4211/1)

## **🧩 Problem Description**

Given a string `s` consisting only of **lowercase alphabetic characters**, check whether it is possible to **remove at most one character** such that the frequency of each distinct character in the string becomes the same. Return `true` if it is possible; otherwise, return `false`.


## Code(C++)
```cpp
class Solution {
public:
    bool sameFreq(string& s) {
        vector<int> freq(26);
        for (char c : s) freq[c - 'a']++;
        unordered_map<int, int> m;
        for (int f : freq) if (f) m[f]++;
        if (m.size() == 1) return true;
        if (m.size() == 2) {
            auto a = m.begin(), b = next(a);
            int f1 = a->first, c1 = a->second;
            int f2 = b->first, c2 = b->second;
            return (f1 == 1 && c1 == 1) || (f2 == 1 && c2 == 1) ||
                  (abs(f1 - f2) == 1 && ((f1 > f2 && c1 == 1) || (f2 > f1 && c2 == 1)));
        }
        return false;
    }
};
```

## Code (Java)

```java
class Solution {
    boolean sameFreq(String s) {
        int[] freq = new int[26];
        for (char c : s.toCharArray()) freq[c - 'a']++;
        Map<Integer, Integer> map = new HashMap<>();
        for (int f : freq) if (f > 0) map.put(f, map.getOrDefault(f, 0) + 1);
        if (map.size() == 1) return true;
        if (map.size() == 2) {
            Iterator<Map.Entry<Integer, Integer>> it = map.entrySet().iterator();
            var a = it.next(); var b = it.next();
            int f1 = a.getKey(), c1 = a.getValue(), f2 = b.getKey(), c2 = b.getValue();
            return (f1 == 1 && c1 == 1) || (f2 == 1 && c2 == 1) ||
                   (Math.abs(f1 - f2) == 1 && ((f1 > f2 && c1 == 1) || (f2 > f1 && c2 == 1)));
        }
        return false;
    }
}
```

## Code (Python)

```python
class Solution:
    def sameFreq(self, s: str) -> bool:
        from collections import Counter
        freq = Counter(s)
        count = Counter(freq.values())
        if len(count) == 1:
            return True
        if len(count) == 2:
            (f1, c1), (f2, c2) = count.items()
            return (f1 == 1 and c1 == 1) or (f2 == 1 and c2 == 1) or \
                   (abs(f1 - f2) == 1 and ((f1 > f2 and c1 == 1) or (f2 > f1 and c2 == 1)))
        return False
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
