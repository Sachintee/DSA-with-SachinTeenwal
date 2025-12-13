--- ❤️ ---

# 🚀 _Day 347. Extracting Numbers_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/extracting-numbers/)

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
    # @return an long
    def solve(self, A):
        total = 0
        current = 0
        in_number = False

        for ch in A:
            if ch.isdigit():
                current = current * 10 + int(ch)
                in_number = True
            else:
                if in_number:
                    total += current
                    current = 0
                    in_number = False
        
        # Add the last number if the string ends with digits
        if in_number:
            total += current

        return total

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
