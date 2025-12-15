--- ❤️ ---

# 🚀 _Day 349. Number of Smooth Descent Periods of a Stock_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/number-of-smooth-descent-periods-of-a-stock/)

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
    def getDescentPeriods(self, prices: List[int]) -> int:
        ans = 0
        i, n = 0, len(prices)
        while i < n:
            j = i + 1
            while j < n and prices[j - 1] - prices[j] == 1:
                j += 1
            cnt = j - i
            ans += (1 + cnt) * cnt // 2
            i = j
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
