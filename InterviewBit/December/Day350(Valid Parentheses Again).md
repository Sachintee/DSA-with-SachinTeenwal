--- ❤️ ---

# 🚀 _Day 350. Valid Parentheses Again_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/valid-parentheses-again/)

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
        n = len(A)
        
        dp = [[0]*n for _ in range(n)]
        
        def pair_count(a, b):
            cnt = 0
            if (a == '(' or a == '?') and (b == ')' or b == '?'):
                cnt += 1
            if (a == '{' or a == '?') and (b == '}' or b == '?'):
                cnt += 1
            if (a == '[' or a == '?') and (b == ']' or b == '?'):
                cnt += 1
            return cnt
        
        for length in range(2, n+1, 2):
            for l in range(n - length + 1):
                r = l + length - 1
                total = 0
                
                for k in range(l+1, r+1, 2):
                    pc = pair_count(A[l], A[k])
                    if pc == 0:
                        continue
                    
                    left = dp[l+1][k-1] if l+1 <= k-1 else 1
                    right = dp[k+1][r] if k+1 <= r else 1
                    
                    total = (total + pc * left * right) % MOD
                
                dp[l][r] = total
        
        return dp[0][n-1]

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
