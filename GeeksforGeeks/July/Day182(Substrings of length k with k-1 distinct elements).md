---
title: "🪟 Substrings of Length K with K-1 Distinct Elements | GFG Solution 🔍"
keywords🏷️: ["🪟 substring count", "🔍 sliding window", "📍 frequency array", "📈 string processing", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to find count of substrings of length k with exactly k-1 distinct characters using optimized sliding window technique. 🚀"
date: 📅 2025-07-01
---

# *182. Substrings of Length K with K-1 Distinct Elements*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/substrings-of-length-k-with-k-1-distinct-elements/1)

## **🧩 Problem Description**

Given a string `s` consisting only of **lowercase alphabets** and an integer `k`. Find the count of all substrings of length `k` which have exactly `k-1` distinct characters.


## Code(C++)
```cpp
class Solution {
public:
    int substrCount(string &s, int k) {
        if (k > s.length()) return 0;
        vector<int> cnt(26);
        int ans = 0, d = 0, n = s.length();
        for (int i = 0; i < k - 1; i++) if (++cnt[s[i]-'a'] == 1) d++;
        for (int i = k - 1; i < n; i++) {
            if (++cnt[s[i]-'a'] == 1) d++;
            if (d == k - 1) ans++;
            if (--cnt[s[i-k+1]-'a'] == 0) d--;
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int substrCount(String s, int k) {
        if (k > s.length()) return 0;
        int[] cnt = new int[26];
        int ans = 0, d = 0, n = s.length();
        for (int i = 0; i < k - 1; i++) if (++cnt[s.charAt(i)-'a'] == 1) d++;
        for (int i = k - 1; i < n; i++) {
            if (++cnt[s.charAt(i)-'a'] == 1) d++;
            if (d == k - 1) ans++;
            if (--cnt[s.charAt(i-k+1)-'a'] == 0) d--;
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def substrCount(self, s, k):
        if k > len(s): return 0
        cnt = [0]*26
        ans = d = 0
        for i in range(k-1):
            if cnt[ord(s[i])-97] == 0: d += 1
            cnt[ord(s[i])-97] += 1
        for i in range(k-1, len(s)):
            if cnt[ord(s[i])-97] == 0: d += 1
            cnt[ord(s[i])-97] += 1
            if d == k - 1: ans += 1
            idx = ord(s[i-k+1])-97
            cnt[idx] -= 1
            if cnt[idx] == 0: d -= 1
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
