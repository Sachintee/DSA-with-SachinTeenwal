--- ❤️ ---

# 🚀 _Day 133. Total Characters in String After Transformations I_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/total-characters-in-string-after-transformations-i/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int lengthAfterTransformations(string s, int t) {
        const int mod = 1e9 + 7;
        vector<vector<int>> f(t + 1, vector<int>(26, 0));

        for (char c : s) {
            f[0][c - 'a']++;
        }

        for (int i = 1; i <= t; ++i) {
            f[i][0] = f[i - 1][25] % mod;
            f[i][1] = (f[i - 1][0] + f[i - 1][25]) % mod;
            for (int j = 2; j < 26; ++j) {
                f[i][j] = f[i - 1][j - 1] % mod;
            }
        }

        int ans = 0;
        for (int j = 0; j < 26; ++j) {
            ans = (ans + f[t][j]) % mod;
        }

        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int lengthAfterTransformations(String s, int t) {
        final int mod = (int) 1e9 + 7;
        int[][] f = new int[t + 1][26];
        for (char c : s.toCharArray()) {
            f[0][c - 'a']++;
        }
        for (int i = 1; i <= t; ++i) {
            f[i][0] = f[i - 1][25] % mod;
            f[i][1] = (f[i - 1][0] + f[i - 1][25]) % mod;
            for (int j = 2; j < 26; j++) {
                f[i][j] = f[i - 1][j - 1] % mod;
            }
        }

        int ans = 0;
        for (int j = 0; j < 26; ++j) {
            ans = (ans + f[t][j]) % mod;
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def lengthAfterTransformations(self, s: str, t: int) -> int:
        f = [[0] * 26 for _ in range(t + 1)]
        for c in s:
            f[0][ord(c) - ord("a")] += 1
        for i in range(1, t + 1):
            f[i][0] = f[i - 1][25]
            f[i][1] = f[i - 1][0] + f[i - 1][25]
            for j in range(2, 26):
                f[i][j] = f[i - 1][j - 1]
        mod = 10**9 + 7
        return sum(f[t]) % mod
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
