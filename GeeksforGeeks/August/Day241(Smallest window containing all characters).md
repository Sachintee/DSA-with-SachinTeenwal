---
title: "🔤 Smallest Window Containing All Characters | GFG Solution 🪟"
keywords🏷️: ["🔤 smallest window", "🪟 sliding window", "📍 two pointers", "📈 frequency array", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Smallest Window Containing All Characters problem: find minimum length substring containing all characters of pattern using sliding window technique. 🚀"
date: 📅 2025-08-29
---

# *241. Smallest Window Containing All Characters*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/smallest-window-in-a-string-containing-all-the-characters-of-another-string-1587115621/1)

## **🧩 Problem Description**

You are given two strings `s` and `p`. Your task is to find the **smallest substring** in `s` that contains **all characters** (including duplicates) of the string `p`. Return an empty string if no such substring exists.

If there are multiple substrings of the same minimum length, return the one with the **least starting index**.


## Code(C++)
```cpp
class Solution {
public:
    string smallestWindow(string &s, string &p) {
        int m = s.size(), n = p.size();
        if (m < n) return "";
        int freq[256] = {0}, window[256] = {0};
        for (char c : p) freq[c]++;
        int formed = 0, required = 0;
        for (int i = 0; i < 256; i++) if (freq[i] > 0) required++;
        int l = 0, r = 0, minLen = INT_MAX, minStart = 0;
        while (r < m) {
            window[s[r]]++;
            if (freq[s[r]] > 0 && window[s[r]] == freq[s[r]]) formed++;
            while (l <= r && formed == required) {
                if (r - l + 1 < minLen) {
                    minLen = r - l + 1;
                    minStart = l;
                }
                window[s[l]]--;
                if (freq[s[l]] > 0 && window[s[l]] < freq[s[l]]) formed--;
                l++;
            }
            r++;
        }
        return minLen == INT_MAX ? "" : s.substr(minStart, minLen);
    }
};
```

## Code (Java)

```java
class Solution {
    public static String smallestWindow(String s, String p) {
        int m = s.length(), n = p.length();
        if (m < n) return "";
        int[] need = new int[256];
        for (char c : p.toCharArray()) need[c]++;
        int missing = n, start = 0, minStart = 0, minLen = Integer.MAX_VALUE;
        for (int end = 0; end < m; end++) {
            if (need[s.charAt(end)]-- > 0) missing--;
            while (missing == 0) {
                if (end - start + 1 < minLen) {
                    minLen = end - start + 1;
                    minStart = start;
                }
                if (++need[s.charAt(start++)] > 0) missing++;
            }
        }
        return minLen == Integer.MAX_VALUE ? "" : s.substring(minStart, minStart + minLen);
    }
}
```

## Code (Python3)

```python
class Solution:
    def smallestWindow(self, s, p):
        m, n = len(s), len(p)
        if m < n: return ""
        need = [0] * 256
        for c in p: need[ord(c)] += 1
        missing, start, min_start, min_len = n, 0, 0, float('inf')
        for end in range(m):
            if need[ord(s[end])] > 0: missing -= 1
            need[ord(s[end])] -= 1
            while missing == 0:
                if end - start + 1 < min_len:
                    min_len = end - start + 1
                    min_start = start
                need[ord(s[start])] += 1
                if need[ord(s[start])] > 0: missing += 1
                start += 1
        return "" if min_len == float('inf') else s[min_start:min_start + min_len]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
