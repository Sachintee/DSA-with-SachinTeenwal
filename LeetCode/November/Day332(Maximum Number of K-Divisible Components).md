--- ❤️ ---

# 🚀 _Day 332. Maximum Number of K-Divisible Components_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/maximum-number-of-k-divisible-components/description/)

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
    def maxKDivisibleComponents(
        self, n: int, edges: List[List[int]], values: List[int], k: int
    ) -> int:
        def dfs(i: int, fa: int) -> int:
            s = values[i]
            for j in g[i]:
                if j != fa:
                    s += dfs(j, i)
            nonlocal ans
            ans += s % k == 0
            return s

        g = [[] for _ in range(n)]
        for a, b in edges:
            g[a].append(b)
            g[b].append(a)
        ans = 0
        dfs(0, -1)
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
