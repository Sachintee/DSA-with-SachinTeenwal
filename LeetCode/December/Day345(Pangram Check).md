--- ❤️ ---

# 🚀 _Day 345. Pangram Check_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/pangram-check/)

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
    # @param A : list of strings
    # @return an integer
    def solve(self, A):
        seen = set()

        for word in A:
            for ch in word:
                if 'a' <= ch <= 'z':   # ensure lowercase alphabet
                    seen.add(ch)
        
        return 1 if len(seen) == 26 else 0

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
