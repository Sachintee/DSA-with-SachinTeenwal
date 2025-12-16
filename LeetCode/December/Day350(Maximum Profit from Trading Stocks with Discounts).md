--- ❤️ ---

# 🚀 _Day 350. Maximum Profit from Trading Stocks with Discounts_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/maximum-profit-from-trading-stocks-with-discounts/description/)

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
    def maxProfit(
        self,
        n: int,
        present: List[int],
        future: List[int],
        hierarchy: List[List[int]],
        budget: int,
    ) -> int:
        max = lambda a, b: a if a > b else b
        g = [[] for _ in range(n + 1)]
        for u, v in hierarchy:
            g[u].append(v)

        def dfs(u: int):
            nxt = [[0, 0] for _ in range(budget + 1)]
            for v in g[u]:
                fv = dfs(v)
                for j in range(budget, -1, -1):
                    for jv in range(j + 1):
                        for pre in (0, 1):
                            val = nxt[j - jv][pre] + fv[jv][pre]
                            if val > nxt[j][pre]:
                                nxt[j][pre] = val

            f = [[0, 0] for _ in range(budget + 1)]
            price = future[u - 1]

            for j in range(budget + 1):
                for pre in (0, 1):
                    cost = present[u - 1] // (pre + 1)
                    if j >= cost:
                        f[j][pre] = max(nxt[j][0], nxt[j - cost][1] + (price - cost))
                    else:
                        f[j][pre] = nxt[j][0]

            return f

        return dfs(1)[budget][0]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
