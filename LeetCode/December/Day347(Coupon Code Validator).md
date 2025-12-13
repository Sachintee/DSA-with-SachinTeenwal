--- ❤️ ---

# 🚀 _Day 347. Coupon Code Validator_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/coupon-code-validator/description/)

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
    def validateCoupons(
        self, code: List[str], businessLine: List[str], isActive: List[bool]
    ) -> List[str]:
        def check(s: str) -> bool:
            if not s:
                return False
            for c in s:
                if not (c.isalpha() or c.isdigit() or c == "_"):
                    return False
            return True

        idx = []
        bs = {"electronics", "grocery", "pharmacy", "restaurant"}
        for i, (c, b, a) in enumerate(zip(code, businessLine, isActive)):
            if a and b in bs and check(c):
                idx.append(i)
        idx.sort(key=lambda i: (businessLine[i], code[i]))
        return [code[i] for i in idx]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
