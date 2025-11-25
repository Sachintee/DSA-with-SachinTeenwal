--- ❤️ ---

# 🚀 _Day 329. Word Count_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/word-count/)

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
        i = 0

        while i < n:
            # skip spaces
            while i < n and A[i] == ' ':
                i += 1

            # if we find a letter → a new word starts
            if i < n and A[i] != ' ':
                count += 1

            # skip this word
            while i < n and A[i] != ' ':
                i += 1

        return count

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
