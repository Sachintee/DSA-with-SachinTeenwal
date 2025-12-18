--- ❤️ ---

# 🚀 _Day 352. Best Time to Buy and Sell Stock using Strategy_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-using-strategy/)

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
    def maxProfit(self, prices: List[int], strategy: List[int], k: int) -> int:
        n = len(prices)
        s = [0] * (n + 1)
        t = [0] * (n + 1)
        for i, (a, b) in enumerate(zip(prices, strategy), 1):
            s[i] = s[i - 1] + a * b
            t[i] = t[i - 1] + a
        ans = s[n]
        for i in range(k, n + 1):
            ans = max(ans, s[n] - (s[i] - s[i - k]) + t[i] - t[i - k // 2])
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
