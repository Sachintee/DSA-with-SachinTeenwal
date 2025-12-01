--- ❤️ ---

# 🚀 _Day 335. Kingdom of Friendship_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/kingdom-of-friendship/)

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
        n = len(A)
        count = 0

        for i in range(n):
            j = A[i] - 1   # best friend index (convert 1-based to 0-based)
            if j != i and A[j] - 1 == i:
                count += 1

        return count // 2   # each pair counted twice

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
