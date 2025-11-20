---
title: "🔄 Make Strings Equal | GFG Solution 🔍"
keywords🏷️: ["🔄 string transformation", "🔍 shortest path", "📈 Floyd-Warshall", "🎯 graph algorithms", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to Make Strings Equal problem: find minimum cost to transform two strings to be identical using Floyd-Warshall algorithm for shortest path computation. 🚀"
date: 📅 2025-11-20
---

# *324. Make Strings Equal*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/make-strings-equal--150209/1)

## **🧩 Problem Description**

You are given two strings `s` and `t` consisting of lowercase English letters. You are also given a 2D array `transform[][]` of size `n*2`, where each entry `[x, y]` means you can transform character `x` into character `y`, and an array `cost[]`, where `cost[i]` is the cost of transforming `transform[i][0]` into `transform[i][1]`.

Your task is to find the **minimum total cost** required to make the strings identical by transforming characters. You can apply any transformation any number of times on either string. If it is impossible to make the two strings identical, return `-1`.


## Code(C++)
```cpp
class Solution {
public:
    int minCost(string &s, string &t, vector<vector<char>> &transform, vector<int> &cost) {
        const int INF = 1e9;
        vector<vector<int>> d(26, vector<int>(26, INF));
        for (int i = 0; i < 26; i++) d[i][i] = 0;
        for (int i = 0; i < transform.size(); i++) 
            d[transform[i][0] - 'a'][transform[i][1] - 'a'] = min(d[transform[i][0] - 'a'][transform[i][1] - 'a'], cost[i]);
        for (int k = 0; k < 26; k++)
            for (int i = 0; i < 26; i++)
                for (int j = 0; j < 26; j++)
                    if (d[i][k] < INF && d[k][j] < INF)
                        d[i][j] = min(d[i][j], d[i][k] + d[k][j]);
        int res = 0;
        for (int i = 0; i < s.size(); i++) {
            if (s[i] == t[i]) continue;
            int mn = INF, a = s[i] - 'a', b = t[i] - 'a';
            for (int c = 0; c < 26; c++)
                if (d[a][c] < INF && d[b][c] < INF)
                    mn = min(mn, d[a][c] + d[b][c]);
            if (mn == INF) return -1;
            res += mn;
        }
        return res;
    }
};
```

## Code (Java)

```java
class Solution {
    public int minCost(String s, String t, char[][] transform, int[] cost) {
        final int INF = (int)1e9;
        int[][] d = new int[26][26];
        for (int i = 0; i < 26; i++) {
            Arrays.fill(d[i], INF);
            d[i][i] = 0;
        }
        for (int i = 0; i < transform.length; i++)
            d[transform[i][0] - 'a'][transform[i][1] - 'a'] = Math.min(d[transform[i][0] - 'a'][transform[i][1] - 'a'], cost[i]);
        for (int k = 0; k < 26; k++)
            for (int i = 0; i < 26; i++)
                for (int j = 0; j < 26; j++)
                    if (d[i][k] < INF && d[k][j] < INF)
                        d[i][j] = Math.min(d[i][j], d[i][k] + d[k][j]);
        int res = 0;
        for (int i = 0; i < s.length(); i++) {
            if (s.charAt(i) == t.charAt(i)) continue;
            int mn = INF, a = s.charAt(i) - 'a', b = t.charAt(i) - 'a';
            for (int c = 0; c < 26; c++)
                if (d[a][c] < INF && d[b][c] < INF)
                    mn = Math.min(mn, d[a][c] + d[b][c]);
            if (mn == INF) return -1;
            res += mn;
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def minCost(self, s, t, transform, cost):
        INF = int(1e9)
        d = [[INF] * 26 for _ in range(26)]
        for i in range(26): d[i][i] = 0
        for i in range(len(transform)):
            u, v = ord(transform[i][0]) - ord('a'), ord(transform[i][1]) - ord('a')
            d[u][v] = min(d[u][v], cost[i])
        for k in range(26):
            for i in range(26):
                for j in range(26):
                    if d[i][k] < INF and d[k][j] < INF:
                        d[i][j] = min(d[i][j], d[i][k] + d[k][j])
        res = 0
        for i in range(len(s)):
            if s[i] == t[i]: continue
            mn, a, b = INF, ord(s[i]) - ord('a'), ord(t[i]) - ord('a')
            for c in range(26):
                if d[a][c] < INF and d[b][c] < INF:
                    mn = min(mn, d[a][c] + d[b][c])
            if mn == INF: return -1
            res += mn
        return res
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
