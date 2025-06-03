---
title: "🔡 Substrings with K Distinct | GFG Solution 🎯"
keywords📌: ["👉 substrings k distinct", "🤝 sliding window", "🔢 frequency count", "🧪 hashmap technique", "📈 string pattern", "📘 GFG", "🏁 competitive programming", "💪 string problems", "📚 DSA"]
description: "✅ GFG solution to the Substrings with K Distinct Characters problem using sliding window and optimized frequency count. 🚀"
date: 📅 2025-06-03
---

# *154. Substrings with K Distinct*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/count-number-of-substrings-with-exactly-k-distinct-characters/)

## **🧩 Problem Description**

Given a string consisting of lowercase characters and an integer `k`, the task is to count all possible substrings (not necessarily distinct) that have **exactly `k` distinct characters**.



## Code(C++)
```cpp
class Solution {
  public:
    int count(string &s, int k) {
        int n = s.length(), ans = 0;
        vector<int> freq(26, 0);
        int i = 0, distinct = 0;
        for (int j = 0; j < n; ++j) {
            if (++freq[s[j] - 'a'] == 1) ++distinct;
            while (distinct > k)
                if (--freq[s[i++] - 'a'] == 0) --distinct;
            ans += j - i + 1;
        }
        return ans;
    }
    
    int countSubstr(string &s, int k) {
        return count(s, k) - count(s, k - 1);
    }
};
```

## Code (Java)

```java
class Solution {
    int count(String s, int k) {
        int[] freq = new int[26];
        int i = 0, ans = 0, distinct = 0;
        for (int j = 0; j < s.length(); ++j) {
            if (++freq[s.charAt(j) - 'a'] == 1) ++distinct;
            while (distinct > k)
                if (--freq[s.charAt(i++) - 'a'] == 0) --distinct;
            ans += j - i + 1;
        }
        return ans;
    }

    int countSubstr(String s, int k) {
        return count(s, k) - count(s, k - 1);
    }
}
```

## Code (Python)

```python
class Solution:
    def count(self, s, k):
        freq = [0] * 26
        i = ans = distinct = 0
        for j in range(len(s)):
            if freq[ord(s[j]) - ord('a')] == 0:
                distinct += 1
            freq[ord(s[j]) - ord('a')] += 1
            while distinct > k:
                freq[ord(s[i]) - ord('a')] -= 1
                if freq[ord(s[i]) - ord('a')] == 0:
                    distinct -= 1
                i += 1
            ans += j - i + 1
        return ans

    def countSubstr(self, s, k):
        return self.count(s, k) - self.count(s, k - 1)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
