--- ❤️ ---

# 🚀 _Day 218. Intersecting Chords in a Circle_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/intersecting-chords-in-a-circle/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int chordCnt(int A) {
        const int MOD = 1e9 + 7;
        vector<long long> dp(A + 1, 0);
        dp[0] = 1;

        for (int n = 1; n <= A; ++n) {
            for (int i = 0; i < n; ++i) {
                dp[n] = (dp[n] + dp[i] * dp[n - 1 - i]) % MOD;
            }
        }

        return dp[A];
    }
};

```

## Code (Java)

```java
public class Solution {
    public int chordCnt(int A) {
        int MOD = 1000000007;
        long[] dp = new long[A + 1];
        dp[0] = 1;

        for (int n = 1; n <= A; n++) {
            for (int i = 0; i < n; i++) {
                dp[n] = (dp[n] + dp[i] * dp[n - 1 - i]) % MOD;
            }
        }

        return (int) dp[A];
    }
}

```

## Code (Python)

```python
class Solution:
    def chordCnt(self, A):
        MOD = 10**9 + 7
        dp = [0] * (A + 1)
        dp[0] = 1  # Base case: 1 way for 0 chords (empty set)

        for n in range(1, A + 1):
            for i in range(n):
                dp[n] = (dp[n] + dp[i] * dp[n - 1 - i]) % MOD

        return dp[A]

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
