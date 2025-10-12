--- ❤️ ---

# 🚀 _Day 285. Find Sum of Array Product of Magical Sequences_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/find-sum-of-array-product-of-magical-sequences/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
const int N = 31;
const long long MOD = 1'000'000'007;

long long f[N], g[N];

long long qpow(long long a, long long k) {
    long long res = 1;
    while (k) {
        if (k & 1) res = res * a % MOD;
        a = a * a % MOD;
        k >>= 1;
    }
    return res;
}

int init = []() {
    f[0] = g[0] = 1;
    for (int i = 1; i < N; ++i) {
        f[i] = f[i - 1] * i % MOD;
        g[i] = qpow(f[i], MOD - 2);
    }
    return 0;
}();

long long comb(int m, int n) {
    return f[m] * g[n] % MOD * g[m - n] % MOD;
}

class Solution {
    vector<vector<vector<vector<long long>>>> dp;

    long long dfs(int i, int j, int k, int st) {
        if (k < 0 || (i == nums.size() && j > 0)) {
            return 0;
        }
        if (i == nums.size()) {
            while (st > 0) {
                k -= (st & 1);
                st >>= 1;
            }
            return k == 0 ? 1 : 0;
        }

        long long& res = dp[i][j][k][st];
        if (res != -1) {
            return res;
        }

        res = 0;
        for (int t = 0; t <= j; ++t) {
            int nt = t + st;
            int nk = k - (nt & 1);
            long long p = qpow(nums[i], t);
            long long tmp = comb(j, t) * p % MOD * dfs(i + 1, j - t, nk, nt >> 1) % MOD;
            res = (res + tmp) % MOD;
        }
        return res;
    }

public:
    int magicalSum(int m, int k, vector<int>& nums) {
        int n = nums.size();
        this->nums = nums;
        dp.assign(n + 1, vector<vector<vector<long long>>>(m + 1, vector<vector<long long>>(k + 1, vector<long long>(N, -1))));
        return dfs(0, m, k, 0);
    }

private:
    vector<int> nums;
};
```

## Code (Java)

```java
class Solution {
    static final int N = 31;
    static final long MOD = 1_000_000_007L;
    private static final long[] f = new long[N];
    private static final long[] g = new long[N];
    private Long[][][][] dp;

    static {
        f[0] = 1;
        g[0] = 1;
        for (int i = 1; i < N; ++i) {
            f[i] = f[i - 1] * i % MOD;
            g[i] = qpow(f[i], MOD - 2);
        }
    }

    public static long qpow(long a, long k) {
        long res = 1;
        while (k != 0) {
            if ((k & 1) == 1) {
                res = res * a % MOD;
            }
            a = a * a % MOD;
            k >>= 1;
        }
        return res;
    }

    public static long comb(int m, int n) {
        return f[m] * g[n] % MOD * g[m - n] % MOD;
    }

    public int magicalSum(int m, int k, int[] nums) {
        int n = nums.length;
        dp = new Long[n + 1][m + 1][k + 1][N];
        long ans = dfs(0, m, k, 0, nums);
        return (int) ans;
    }

    private long dfs(int i, int j, int k, int st, int[] nums) {
        if (k < 0 || (i == nums.length && j > 0)) {
            return 0;
        }
        if (i == nums.length) {
            while (st > 0) {
                k -= (st & 1);
                st >>= 1;
            }
            return k == 0 ? 1 : 0;
        }

        if (dp[i][j][k][st] != null) {
            return dp[i][j][k][st];
        }

        long res = 0;
        for (int t = 0; t <= j; t++) {
            int nt = t + st;
            int nk = k - (nt & 1);
            long p = qpow(nums[i], t);
            long tmp = comb(j, t) * p % MOD * dfs(i + 1, j - t, nk, nt >> 1, nums) % MOD;
            res = (res + tmp) % MOD;
        }

        return dp[i][j][k][st] = res;
    }
}
```

## Code (Python)

```python
mx = 30
mod = 10**9 + 7
f = [1] + [0] * mx
g = [1] + [0] * mx

for i in range(1, mx + 1):
    f[i] = f[i - 1] * i % mod
    g[i] = pow(f[i], mod - 2, mod)


def comb(m: int, n: int) -> int:
    return f[m] * g[n] * g[m - n] % mod


class Solution:
    def magicalSum(self, m: int, k: int, nums: List[int]) -> int:
        @cache
        def dfs(i: int, j: int, k: int, st: int) -> int:
            if k < 0 or (i == len(nums) and j > 0):
                return 0
            if i == len(nums):
                while st:
                    k -= st & 1
                    st >>= 1
                return int(k == 0)
            res = 0
            for t in range(j + 1):
                nt = t + st
                p = pow(nums[i], t, mod)
                nk = k - (nt & 1)
                res += comb(j, t) * p * dfs(i + 1, j - t, nk, nt >> 1)
                res %= mod
            return res

        ans = dfs(0, m, k, 0)
        dfs.cache_clear()
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
