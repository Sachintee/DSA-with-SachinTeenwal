--- ❤️ ---

# 🚀 _Day 325. Maximize the Matrix_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/maximize-the-matrix/)

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
    def solve(self, A, B, C):

        # flatten table size
        n = len(A)
        m = len(A[0])

        # helper: check if we can make all values >= X
        def can(X):
            ops_used = 0

            for row in A:
                need = [0] * m
                for j in range(m):
                    if row[j] < X:
                        need[j] = (X - row[j] + 1) // 2   # how many +2 ops needed

                # sliding window greedy to apply increments
                add = [0] * (m + 1)
                curr = 0

                for j in range(m):
                    curr += add[j]

                    # how many more increments this cell still needs:
                    if curr < need[j]:
                        extra = need[j] - curr
                        ops_used += extra
                        if ops_used > B:
                            return False

                        curr += extra
                        if j + C <= m:
                            add[j + C] -= extra

            return ops_used <= B

        # binary search answer
        low = min(min(row) for row in A)
        high = low + 2 * B + 5   # safe upper bound

        ans = low

        while low <= high:
            mid = (low + high) // 2
            if can(mid):
                ans = mid
                low = mid + 1
            else:
                high = mid - 1

        return ans

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
