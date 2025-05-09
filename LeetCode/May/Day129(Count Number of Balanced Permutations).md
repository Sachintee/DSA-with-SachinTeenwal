--- ❤️ ---

# 🚀 _Day 129. Count Number of Balanced Permutations_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/count-number-of-balanced-permutations/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
using ll = long long;
const int MX = 80;
const int MOD = 1e9 + 7;
ll c[MX][MX];

auto init = [] {
    c[0][0] = 1;
    for (int i = 1; i < MX; ++i) {
        c[i][0] = 1;
        for (int j = 1; j <= i; ++j) {
            c[i][j] = (c[i - 1][j] + c[i - 1][j - 1]) % MOD;
        }
    }
    return 0;
}();

class Solution {
public:
    int countBalancedPermutations(string num) {
        int cnt[10]{};
        int s = 0;
        for (char& c : num) {
            ++cnt[c - '0'];
            s += c - '0';
        }
        if (s % 2) {
            return 0;
        }
        int n = num.size();
        int m = n / 2 + 1;
        int f[10][s / 2 + 1][m][m + 1];
        memset(f, -1, sizeof(f));
        auto dfs = [&](this auto&& dfs, int i, int j, int a, int b) -> int {
            if (i > 9) {
                return ((j | a | b) == 0 ? 1 : 0);
            }
            if (a == 0 && j) {
                return 0;
            }
            if (f[i][j][a][b] != -1) {
                return f[i][j][a][b];
            }
            int ans = 0;
            for (int l = 0; l <= min(cnt[i], a); ++l) {
                int r = cnt[i] - l;
                if (r >= 0 && r <= b && l * i <= j) {
                    int t = c[a][l] * c[b][r] % MOD * dfs(i + 1, j - l * i, a - l, b - r) % MOD;
                    ans = (ans + t) % MOD;
                }
            }
            return f[i][j][a][b] = ans;
        };
        return dfs(0, s / 2, n / 2, (n + 1) / 2);
    }
};
```

## Code (Java)

```java
class Solution {
    private final int[] cnt = new int[10];
    private final int mod = (int) 1e9 + 7;
    private Integer[][][][] f;
    private long[][] c;

    public int countBalancedPermutations(String num) {
        int s = 0;
        for (char c : num.toCharArray()) {
            cnt[c - '0']++;
            s += c - '0';
        }
        if (s % 2 == 1) {
            return 0;
        }
        int n = num.length();
        int m = n / 2 + 1;
        f = new Integer[10][s / 2 + 1][m][m + 1];
        c = new long[m + 1][m + 1];
        c[0][0] = 1;
        for (int i = 1; i <= m; i++) {
            c[i][0] = 1;
            for (int j = 1; j <= i; j++) {
                c[i][j] = (c[i - 1][j] + c[i - 1][j - 1]) % mod;
            }
        }
        return dfs(0, s / 2, n / 2, (n + 1) / 2);
    }

    private int dfs(int i, int j, int a, int b) {
        if (i > 9) {
            return ((j | a | b) == 0) ? 1 : 0;
        }
        if (a == 0 && j != 0) {
            return 0;
        }
        if (f[i][j][a][b] != null) {
            return f[i][j][a][b];
        }
        int ans = 0;
        for (int l = 0; l <= Math.min(cnt[i], a); ++l) {
            int r = cnt[i] - l;
            if (r >= 0 && r <= b && l * i <= j) {
                int t = (int) (c[a][l] * c[b][r] % mod * dfs(i + 1, j - l * i, a - l, b - r) % mod);
                ans = (ans + t) % mod;
            }
        }
        return f[i][j][a][b] = ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def countBalancedPermutations(self, num: str) -> int:
        @cache
        def dfs(i: int, j: int, a: int, b: int) -> int:
            if i > 9:
                return (j | a | b) == 0
            if a == 0 and j:
                return 0
            ans = 0
            for l in range(min(cnt[i], a) + 1):
                r = cnt[i] - l
                if 0 <= r <= b and l * i <= j:
                    t = comb(a, l) * comb(b, r) * dfs(i + 1, j - l * i, a - l, b - r)
                    ans = (ans + t) % mod
            return ans

        nums = list(map(int, num))
        s = sum(nums)
        if s % 2:
            return 0
        n = len(nums)
        mod = 10**9 + 7
        cnt = Counter(nums)
        return dfs(0, s // 2, n // 2, (n + 1) // 2)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
