--- ❤️ ---

# 🚀 _Day 320. Dice Rolls_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/dice-rolls/)

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
    def solve(self, A):
        MOD = 10**9 + 7
        
        dp = [0] * (A + 1)
        dp[0] = 1
        
        for i in range(1, A + 1):
            dp[i] = dp[i-1]
            if i >= 2: dp[i] = (dp[i] + dp[i-2]) % MOD
            if i >= 3: dp[i] = (dp[i] + dp[i-3]) % MOD
            if i >= 4: dp[i] = (dp[i] + dp[i-4]) % MOD
            if i >= 5: dp[i] = (dp[i] + dp[i-5]) % MOD
            if i >= 6: dp[i] = (dp[i] + dp[i-6]) % MOD
    
        return dp[A] % MOD

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
