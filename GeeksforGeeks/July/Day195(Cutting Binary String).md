---
title: "🔪 Cutting Binary String | GFG Solution ⚡"
keywords🏷️: ["🔪 binary string", "🔍 dynamic programming", "⚡ power of 5", "🎯 string splitting", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Cutting Binary String problem: find minimum cuts to split binary string into substrings representing powers of 5 using dynamic programming. 🚀"
date: 📅 2025-07-14
---

# *195. Cutting Binary String*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/cutting-binary-string1342/1)

## **🧩 Problem Description**

You are given a binary string `s` consisting only of characters '0' and '1'. Your task is to split this string into the **minimum number of non-empty substrings** such that:

- Each substring represents a **power of 5** in decimal (e.g., 1, 5, 25, 125, ...).
- No substring should have **leading zeros**.

Return the minimum number of such pieces the string can be divided into.

**Note:** If it is not possible to split the string in this way, return -1.


## Code(C++)
```cpp
class Solution {
public:
    int cuts(string s) {
        if (s[0] == '0') return -1;
        int n = s.size();
        unordered_set<long long> powers;
        for (long long p = 1; p <= 1e9; p *= 5) powers.insert(p);
        vector<int> dp(n + 1, n + 1);
        dp[n] = 0;
        for (int i = n - 1; i >= 0; --i) {
            if (s[i] == '0') continue;
            long long num = 0;
            for (int j = i; j < n && num <= 1e9; ++j) {
                num = (num << 1) + (s[j] & 1);
                if (powers.count(num) && dp[j + 1] < n + 1)
                    dp[i] = min(dp[i], 1 + dp[j + 1]);
            }
        }
        return dp[0] > n ? -1 : dp[0];
    }
};
```

## Code (Java)

```java
class Solution {
    public int cuts(String s) {
        if (s.charAt(0) == '0') return -1;
        int n = s.length();
        Set<Long> powers = new HashSet<>();
        for (long p = 1; p <= 1000000000L; p *= 5) powers.add(p);
        int[] dp = new int[n + 1];
        Arrays.fill(dp, n + 1);
        dp[n] = 0;
        for (int i = n - 1; i >= 0; --i) {
            if (s.charAt(i) == '0') continue;
            long num = 0;
            for (int j = i; j < n && num <= 1000000000L; ++j) {
                num = (num << 1) + (s.charAt(j) - '0');
                if (powers.contains(num) && dp[j + 1] <= n)
                    dp[i] = Math.min(dp[i], 1 + dp[j + 1]);
            }
        }
        return dp[0] > n ? -1 : dp[0];
    }
}
```

## Code (Python)

```python
class Solution:
    def cuts(self, s):
        if s[0] == '0': return -1
        n = len(s)
        powers = set()
        p = 1
        while p <= 10**9:
            powers.add(p)
            p *= 5
        dp = [n + 1] * (n + 1)
        dp[n] = 0
        for i in range(n - 1, -1, -1):
            if s[i] == '0': continue
            num = 0
            for j in range(i, n):
                num = (num << 1) + int(s[j])
                if num > 10**9: break
                if num in powers and dp[j + 1] <= n:
                    dp[i] = min(dp[i], 1 + dp[j + 1])
        return -1 if dp[0] > n else dp[0]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
