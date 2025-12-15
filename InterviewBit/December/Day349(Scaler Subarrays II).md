--- ❤️ ---

# 🚀 _Day 349. Scaler Subarrays II_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/scaler-subarrays-ii/)

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
        n = len(A)

        left = [-1]*n
        right = [n]*n

        stack = []
        for i in range(n):
            while stack and A[stack[-1]] < A[i]:
                stack.pop()
            left[i] = stack[-1] if stack else -1
            stack.append(i)

        stack = []
        for i in range(n-1, -1, -1):
            while stack and A[stack[-1]] <= A[i]:
                stack.pop()
            right[i] = stack[-1] if stack else n
            stack.append(i)

        ans = 0

        for i in range(n):
            L = i - left[i]
            R = right[i] - i
            target = A[i] % B

            freq = {}
            for l in range(i, left[i], -1):
                val = A[l] % B
                freq[val] = freq.get(val, 0) + 1

            for r in range(i, right[i]):
                need = (target - A[r] % B) % B
                ans = (ans + freq.get(need, 0)) % MOD

        return ans

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
