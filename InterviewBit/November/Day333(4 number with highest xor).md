--- ❤️ ---

# 🚀 _Day 333. 4 number with highest xor_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/4-number-with-highest-xor/)

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
        from itertools import combinations
        
        best = 0
        for c in combinations(A, 4):
            xor_val = c[0] ^ c[1] ^ c[2] ^ c[3]
            if xor_val > best:
                best = xor_val
        
        return best

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
