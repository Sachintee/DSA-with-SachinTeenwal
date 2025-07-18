--- ❤️ ---

# 🚀 _Day 199. Length of Longest Subsequence_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/length-of-longest-subsequence/)

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
    # @param A : tuple of integers
    # @return an integer
    def longestSubsequenceLength(self, A):
        n = len(A)
        if n == 0:
            return 0

        # LIS from left to right
        lis = [1] * n
        for i in range(n):
            for j in range(i):
                if A[j] < A[i]:
                    lis[i] = max(lis[i], lis[j] + 1)

        # LDS from right to left
        lds = [1] * n
        for i in range(n-1, -1, -1):
            for j in range(n-1, i, -1):
                if A[j] < A[i]:
                    lds[i] = max(lds[i], lds[j] + 1)

        # Combine LIS and LDS for each peak
        max_len = 0
        for i in range(n):
            max_len = max(max_len, lis[i] + lds[i] - 1)

        return max_len

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
