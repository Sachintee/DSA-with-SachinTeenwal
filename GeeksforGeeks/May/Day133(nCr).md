# *133. nCr*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/ncr1019/1)

## **🧩 Problem Description**

Given two integers `n` and `r`, return the value of the binomial coefficient C(n, r), defined as the number of ways to choose `r` objects from a set of `n` without regard to order. It is given by:


## Code(C++)
```cpp
class Solution {
    static const int MOD = 1e9+7;
    long long modexp(long long x, long long y) {
        long long res = 1;
        while (y) {
            if (y & 1) res = res * x % MOD;
            x = x * x % MOD;
            y >>= 1;
        }
        return res;
    }
public:
    int nCr(int n, int r) {
        if (r > n) return 0;
        vector<long long> fact(n+1, 1), inv(n+1);
        for (int i = 1; i <= n; ++i)
            fact[i] = fact[i-1] * i % MOD;
        inv[n] = modexp(fact[n], MOD-2);
        for (int i = n; i > 0; --i)
            inv[i-1] = inv[i] * i % MOD;
        return fact[n] * inv[r] % MOD * inv[n-r] % MOD;
    }
};
```

## Code (Java)

```java
class Solution {
    static final int MOD = (int)1e9+7;
    long modexp(long x, long y) {
        long res = 1;
        while (y > 0) {
            if ((y & 1) == 1) res = res * x % MOD;
            x = x * x % MOD;
            y >>= 1;
        }
        return res;
    }
    public int nCr(int n, int r) {
        if (r > n) return 0;
        long[] fact = new long[n+1], inv = new long[n+1];
        fact[0] = 1;
        for (int i = 1; i <= n; ++i)
            fact[i] = fact[i-1] * i % MOD;
        inv[n] = modexp(fact[n], MOD-2);
        for (int i = n; i > 0; --i)
            inv[i-1] = inv[i] * i % MOD;
        return (int)(fact[n] * inv[r] % MOD * inv[n-r] % MOD);
    }
}
```

## Code (Python)

```python
class Solution:
    MOD = 10**9 + 7

    def power(self, x, y):
        res = 1
        while y:
            if y & 1:
                res = res * x % self.MOD
            x = x * x % self.MOD
            y >>= 1
        return res

    def nCr(self, n: int, r: int) -> int:
        if r > n:
            return 0
        fact = [1] * (n+1)
        for i in range(1, n+1):
            fact[i] = fact[i-1] * i % self.MOD
        inv = [1] * (n+1)
        inv[n] = self.power(fact[n], self.MOD-2)
        for i in range(n, 0, -1):
            inv[i-1] = inv[i] * i % self.MOD
        return fact[n] * inv[r] % self.MOD * inv[n-r] % self.MOD
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
