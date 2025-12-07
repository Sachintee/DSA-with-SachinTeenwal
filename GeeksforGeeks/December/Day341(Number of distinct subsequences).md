---
title: "🔤 Number of Distinct Subsequences | GFG Solution 🔍"
keywords🏷️: ["🔤 distinct subsequences", "🔍 dynamic programming", "📍 string manipulation", "📈 modular arithmetic", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Number of Distinct Subsequences problem: find the count of distinct subsequences of a string using dynamic programming with modulo arithmetic. 🚀"
date: 📅 2025-12-07
---

# *341. Number of Distinct Subsequences*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/number-of-distinct-subsequences0909/1)

## **🧩 Problem Description**

Given a string `str` consisting of lowercase English alphabets, the task is to find the number of distinct subsequences of the string.

**Note:** Answer can be very large, so output will be answer modulo 10^9+7.

A subsequence is a sequence that can be derived from another sequence by deleting zero or more elements without changing the order of the remaining elements. For example, "abc" is a subsequence of "aebdc" but "aec" is not.


## Code(C++)
```cpp
class Solution {
public:
    int distinctSubseq(string& str) {
        int n = str.size(), mod = 1e9 + 7, res = 1;
        vector<int> last(26);
        for (int i = 0; i < n; i++) {
            int idx = str[i] - 'a';
            int cur = (2LL * res % mod - last[idx] + mod) % mod;
            last[idx] = res;
            res = cur;
        }
        return res;
    }
};
```

## Code (Java)

```java

```

## Code (Python)

```python

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
