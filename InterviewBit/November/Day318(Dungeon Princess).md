--- ❤️ ---

# 🚀 _Day 318. Dungeon Princess_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/dungeon-princess/)

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
    def calculateMinimumHP(self, A):
        M, N = len(A), len(A[0])
        dp = [[float('inf')] * (N+1) for _ in range(M+1)]
        
        dp[M][N-1] = dp[M-1][N] = 1  # Dummy boundary values to simplify bottom-right

        for i in range(M-1, -1, -1):
            for j in range(N-1, -1, -1):
                min_health_needed = min(dp[i+1][j], dp[i][j+1]) - A[i][j]
                dp[i][j] = max(1, min_health_needed)

        return dp[0][0]

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
