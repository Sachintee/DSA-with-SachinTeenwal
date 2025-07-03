---
title: "🔤 Longest Substring with K Uniques | GFG Solution 🔍"
keywords🏷️: ["🔤 longest substring", "🔍 sliding window", "📍 two pointers", "📈 frequency array", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Longest Substring with K Uniques problem: find maximum length substring containing exactly k distinct characters using sliding window technique. 🚀"
date: 📅 2025-07-03
---

# *184. Longest Substring with K Uniques*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/longest-k-unique-characters-substring0853/1)

## **🧩 Problem Description**

You are given a string `s` consisting only lowercase alphabets and an integer `k`. Your task is to find the length of the **longest substring** that contains **exactly k distinct characters**.

Note: If no such substring exists, return -1.


## Code(C++)
```cpp
class Solution {
public:
    int longestKSubstr(string &s, int k) {
        int n = s.size(), i = 0, cnt = 0, maxi = -1;
        vector<int> fre(26, 0);
        for (int j = 0; j < n; j++) {
            if (fre[s[j] - 'a']++ == 0) cnt++;
            while (cnt > k) {
                if (--fre[s[i] - 'a'] == 0) cnt--;
                i++;
            }
            if (cnt == k) maxi = max(maxi, j - i + 1);
        }
        return maxi;
    }
};
```

## Code (Java)

```java
class Solution {
    public int longestKSubstr(String s, int k) {
        int[] freq = new int[26];
        int i = 0, cnt = 0, max = -1;
        for (int j = 0; j < s.length(); j++) {
            if (freq[s.charAt(j) - 'a']++ == 0) cnt++;
            while (cnt > k) {
                if (--freq[s.charAt(i) - 'a'] == 0) cnt--;
                i++;
            }
            if (cnt == k) max = Math.max(max, j - i + 1);
        }
        return max;
    }
}
```

## Code (Python)

```python
class Solution:
    def longestKSubstr(self, s, k):
        freq = [0] * 26
        i = cnt = maxi = 0
        for j in range(len(s)):
            if freq[ord(s[j]) - ord('a')] == 0:
                cnt += 1
            freq[ord(s[j]) - ord('a')] += 1
            while cnt > k:
                freq[ord(s[i]) - ord('a')] -= 1
                if freq[ord(s[i]) - ord('a')] == 0:
                    cnt -= 1
                i += 1
            if cnt == k:
                maxi = max(maxi, j - i + 1)
        return maxi if maxi > 0 else -1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
