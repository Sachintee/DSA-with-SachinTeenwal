--- ❤️ ---

# 🚀 _Day 323. Parity-Swapping Integer Minimization_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/parity-swapping-integer-minimization/)

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
        ev = []
        od = []
        for ch in A:
            if (ord(ch) - ord('0')) % 2 == 0:
                ev.append(ch)
            else:
                od.append(ch)

        i = j = 0
        res = []
        le = len(ev)
        lo = len(od)

        while i < le and j < lo:
            # compare numeric values of current fronts
            if ord(ev[i]) <= ord(od[j]):
                res.append(ev[i])
                i += 1
            else:
                res.append(od[j])
                j += 1

        # append remaining
        if i < le:
            res.extend(ev[i:])
        if j < lo:
            res.extend(od[j:])

        return "".join(res)

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
