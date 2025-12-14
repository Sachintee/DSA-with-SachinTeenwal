--- ❤️ ---

# 🚀 _Day 348. Consecutive Losses_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/consecutive-losses/)

## 🎯 **My Approach:**


## Code(C++)
```cpp

```

## Code (Java)

```java

```

## Code (Python)

```python
class Solution:
    def solve(self, A, B):
        MOD = 10**9 + 7
        L = A - B
        n = A + 5

        # factorials
        fact = [1] * n
        for i in range(1, n):
            fact[i] = fact[i-1] * i % MOD

        # inverse factorials
        invfact = [1] * n
        invfact[-1] = pow(fact[-1], MOD-2, MOD)
        for i in range(n-1, 0, -1):
            invfact[i-1] = invfact[i] * i % MOD

        def nCr(n, r):
            if r < 0 or r > n or n < 0:
                return 0
            return fact[n] * invfact[r] % MOD * invfact[n-r] % MOD

        # f(K): max consecutive losses ≤ K
        def f(K):
            res = 0
            for i in range(B + 2):
                rem = L - i * (K + 1)
                if rem < 0:
                    break
                term = nCr(B + 1, i) * nCr(rem + B, B) % MOD
                if i % 2 == 0:
                    res = (res + term) % MOD
                else:
                    res = (res - term) % MOD
            return res % MOD

        ans = []
        prev = 0
        for K in range(1, L + 1):
            cur = f(K)
            ans.append((cur - prev) % MOD)
            prev = cur

        return ans

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
