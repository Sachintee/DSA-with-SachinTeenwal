--- ❤️ ---

# 🚀 _Day 336. Count Number of Trapezoids I_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/count-number-of-trapezoids-i/)

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
    def countTrapezoids(self, points: List[List[int]]) -> int:
        mod = 10**9 + 7
        cnt = Counter(p[1] for p in points)
        ans = s = 0
        for v in cnt.values():
            t = v * (v - 1) // 2
            ans = (ans + s * t) % mod
            s += t
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
