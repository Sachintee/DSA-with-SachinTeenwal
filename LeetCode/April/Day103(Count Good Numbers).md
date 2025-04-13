--- ❤️ ---

# 🚀 _Day 103. Count Good Numbers_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/count-good-numbers/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int countGoodNumbers(long long n) {
        const int mod = 1e9 + 7;
        auto qpow = [](long long x, long long n) -> long long {
            long long res = 1;
            while (n) {
                if ((n & 1) == 1) {
                    res = res * x % mod;
                }
                x = x * x % mod;
                n >>= 1;
            }
            return res;
        };
        return qpow(5, (n + 1) >> 1) * qpow(4, n >> 1) % mod;
    }
};
```

## Code (Java)

```java
class Solution {
    private final int mod = (int) 1e9 + 7;

    public int countGoodNumbers(long n) {
        return (int) (qpow(5, (n + 1) >> 1) * qpow(4, n >> 1) % mod);
    }

    private long qpow(long x, long n) {
        long res = 1;
        while (n != 0) {
            if ((n & 1) == 1) {
                res = res * x % mod;
            }
            x = x * x % mod;
            n >>= 1;
        }
        return res;
    }
}
```

## Code (Python)

```python
class Solution:
    def countGoodNumbers(self, n: int) -> int:
        mod = 10**9 + 7
        return pow(5, (n + 1) >> 1, mod) * pow(4, n >> 1, mod) % mod
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
