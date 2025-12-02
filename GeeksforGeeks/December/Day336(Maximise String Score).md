---
title: "🎯 Maximise String Score | GFG Solution 🚀"
keywords🏷️: ["🎯 string score", "🔍 dynamic programming", "📍 prefix sum", "📈 graph traversal", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Maximise String Score problem: find maximum score by performing valid character jumps using dynamic programming and prefix sum optimization. 🚀"
date: 📅 2025-12-02
---

# *336. Maximise String Score*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/maximise-string-score--172902/1)

## **🧩 Problem Description**

You are given a string `s`, and a list of `jumps[][]` of size n, where each `jumps[i] = [s1, s2]` denotes that you are allowed to jump from character `s1` to `s2` in the forward direction.

Additionally, you are allowed to jump forward from a character to any other occurrence of the same character within the string.

You start at index 0 of the string. After every valid jump from index i to index j, where `s[i] = s1` and `s[j] = s2`, you earn a score equal to the sum of ASCII values of all characters between the jump except for the characters equals `s2`, i.e.

**score(i, j) = sum(ascii(s[k]) for i ≤ k < j and s[k] != s[j]).**

Determine the maximum score that can be achieved by performing a sequence of valid jumps starting from index 0.


## Code(C++)
```cpp
class Solution {
public:
    int maxScore(string &s, vector<vector<char>> &jumps) {
        int n = s.size();
        for (char c = 'a'; c <= 'z'; c++) jumps.push_back({c, c});
        vector<vector<int>> nxt(n, vector<int>(26, -1));
        vector<int> last(26, -1);
        for (int i = n - 1; i >= 0; i--) {
            nxt[i] = last;
            last[s[i] - 'a'] = i;
        }
        vector<vector<int>> ch(26);
        for (auto &j : jumps) ch[j[0] - 'a'].push_back(j[1]);
        vector<int> pre(n + 1);
        for (int i = 0; i < n; i++) pre[i + 1] = pre[i] + s[i];
        vector<int> dp(n);
        for (int i = n - 2; i >= 0; i--) {
            for (int c : ch[s[i] - 'a']) {
                int j = nxt[i][c - 'a'];
                if (j != -1) dp[i] = max(dp[i], pre[j] - pre[i + (c == s[i])] + dp[j]);
            }
        }
        return dp[0];
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
