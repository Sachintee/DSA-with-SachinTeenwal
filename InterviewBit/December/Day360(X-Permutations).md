--- ❤️ ---

# 🚀 _Day 360. X-Permutations_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/x-permutations/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
vector<int> Solution::solve(int A) {
    const int MOD = 1000000007;

    // Factorials
    vector<long long> fact(A + 1, 1), invFact(A + 1, 1);
    for (int i = 1; i <= A; i++)
        fact[i] = fact[i - 1] * i % MOD;

    // Fermat inverse factorial
    invFact[A] = 1;
    long long pw = 1, base = fact[A], exp = MOD - 2;
    while (exp) {
        if (exp & 1) pw = pw * base % MOD;
        base = base * base % MOD;
        exp >>= 1;
    }
    invFact[A] = pw;

    for (int i = A; i > 0; i--)
        invFact[i - 1] = invFact[i] * i % MOD;

    // Derangements
    vector<long long> D(A + 1, 0);
    D[0] = 1;
    if (A >= 1) D[1] = 0;
    for (int i = 2; i <= A; i++)
        D[i] = (i - 1) * (D[i - 1] + D[i - 2]) % MOD;

    // Answer
    vector<int> ans(A + 1);
    for (int X = 0; X <= A; X++) {
        long long comb = fact[A] * invFact[X] % MOD * invFact[A - X] % MOD;
        ans[X] = (int)(comb * D[A - X] % MOD);
    }

    return ans;
}

```

## Code (Java)

```java
import java.util.*;

class Solution {
    static final long MOD = 1000000007;

    public ArrayList<Integer> solve(int A) {
        long[] fact = new long[A + 1];
        long[] invFact = new long[A + 1];
        long[] D = new long[A + 1];

        // Factorials
        fact[0] = 1;
        for (int i = 1; i <= A; i++)
            fact[i] = fact[i - 1] * i % MOD;

        // Inverse factorial using Fermat
        invFact[A] = modPow(fact[A], MOD - 2);
        for (int i = A; i > 0; i--)
            invFact[i - 1] = invFact[i] * i % MOD;

        // Derangements
        D[0] = 1;
        if (A >= 1) D[1] = 0;
        for (int i = 2; i <= A; i++)
            D[i] = (i - 1) * (D[i - 1] + D[i - 2]) % MOD;

        // Answer
        ArrayList<Integer> ans = new ArrayList<>();
        for (int X = 0; X <= A; X++) {
            long comb = fact[A] * invFact[X] % MOD * invFact[A - X] % MOD;
            ans.add((int)(comb * D[A - X] % MOD));
        }

        return ans;
    }

    private long modPow(long base, long exp) {
        long res = 1;
        while (exp > 0) {
            if ((exp & 1) == 1) res = res * base % MOD;
            base = base * base % MOD;
            exp >>= 1;
        }
        return res;
    }
}

```

## Code (Python3)

```python
class Solution:
    def solve(self, A):
        MOD = 1000000007

        # ---------- FACTORIALS ----------
        fact = [1] * (A + 1)
        for i in range(1, A + 1):
            fact[i] = fact[i - 1] * i % MOD

        # ---------- INVERSE FACTORIALS ----------
        invFact = [1] * (A + 1)
        invFact[A] = pow(fact[A], MOD - 2, MOD)
        for i in range(A, 0, -1):
            invFact[i - 1] = invFact[i] * i % MOD

        # ---------- DERANGEMENTS ----------
        D = [0] * (A + 1)
        D[0] = 1
        if A >= 1:
            D[1] = 0
        for i in range(2, A + 1):
            D[i] = (i - 1) * (D[i - 1] + D[i - 2]) % MOD

        # ---------- ANSWER ----------
        ans = []
        for X in range(A + 1):
            comb = fact[A] * invFact[X] % MOD * invFact[A - X] % MOD
            ans.append(comb * D[A - X] % MOD)

        return ans

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
