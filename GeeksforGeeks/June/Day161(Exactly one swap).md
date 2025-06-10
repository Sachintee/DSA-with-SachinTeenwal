---
title: "🔁 Exactly One Swap | GFG Solution 🎯"
keywords🏷️: ["🔁 one swap", "🧠 string permutations", "⚡ efficient counting", "📘 GFG", "📚 DSA", "💻 competitive programming"]
description: "✅ GFG solution to the Exactly One Swap problem: count distinct strings after one swap. Uses hashing & counting. 🚀"
date: 📅 2025-06-10
---
# *161. Exactly One Swap*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/exactly-one-swap--170637/1)

## **🧩 Problem Description**

Given a string **s**, return the **number of distinct strings** that can be obtained by **exactly one swap** of two different indices `(i < j)`.


## Code(C++)
```cpp
class Solution{
public:
    int countStrings(string &s){
        vector<int> m(26);
        int ans = 0;
        for(int i = 0; i < s.size(); ++i){
            ans += i - m[s[i] - 'a'];
            ++m[s[i] - 'a'];
        }
        for(int x : m) if(x > 1){ ++ans; break; }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int countStrings(String s) {
        int[] m = new int[26];
        int ans = 0;
        for (int i = 0; i < s.length(); ++i) {
            ans += i - m[s.charAt(i) - 'a'];
            ++m[s.charAt(i) - 'a'];
        }
        for (int x : m) if (x > 1) { ans++; break; }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def countStrings(self, s):
        m = [0]*26
        ans = 0
        for i, ch in enumerate(s):
            ans += i - m[ord(ch) - 97]
            m[ord(ch) - 97] += 1
        if any(x > 1 for x in m):
            ans += 1
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
