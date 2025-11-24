--- ❤️ ---

# 🚀 _Day 328. Prime calculations_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/prime-calculations/)

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
        
        maxA = 10**6
        
        # Precompute number of distinct prime factors
        pf = [0] * (maxA + 1)
        for i in range(2, maxA + 1):
            if pf[i] == 0:              # prime
                for mult in range(i, maxA + 1, i):
                    pf[mult] += 1
        
        n = len(A)
        dq = []
        ans = 0
        
        for i in range(n):
            # Keep deque monotonic decreasing by pf, but KEEP ties
            while dq and pf[A[dq[-1]]] < pf[A[i]]:
                dq.pop()
            dq.append(i)
            
            # Remove if out of window
            if dq[0] <= i - B:
                dq.pop(0)
            
            # Add result once window is formed
            if i >= B - 1:
                ans = (ans + A[dq[0]]) % MOD
        
        return ans

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
