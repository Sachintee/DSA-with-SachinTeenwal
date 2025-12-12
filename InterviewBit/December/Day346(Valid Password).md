--- ❤️ ---

# 🚀 _Day 346. Valid Password_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/valid-password/)

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
    # @param A : string
    # @return an integer
    def solve(self, A):
        n = len(A)
        
        # Length condition
        if n < 8 or n > 15:
            return 0
        
        has_digit = False
        has_lower = False
        has_upper = False
        has_special = False
        
        specials = set("@#%&!$*")
        
        for ch in A:
            if ch.isdigit():
                has_digit = True
            elif ch.islower():
                has_lower = True
            elif ch.isupper():
                has_upper = True
            elif ch in specials:
                has_special = True
        
        # Check all conditions
        if has_digit and has_lower and has_upper and has_special:
            return 1
        return 0

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
