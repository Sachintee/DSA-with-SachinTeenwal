--- ❤️ ---

# 🚀 _Day 229. New 21 Game_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/new-21-game/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    double new21Game(int n, int k, int maxPts) {
        vector<double> f(k);
        auto dfs = [&](this auto&& dfs, int i) -> double {
            if (i >= k) {
                return i <= n ? 1 : 0;
            }
            if (i == k - 1) {
                return min(n - k + 1, maxPts) * 1.0 / maxPts;
            }
            if (f[i]) {
                return f[i];
            }
            return f[i] = dfs(i + 1) + (dfs(i + 1) - dfs(i + maxPts + 1)) / maxPts;
        };
        return dfs(0);
    }
};
```

## Code (Java)

```java
class Solution {
    private double[] f;
    private int n, k, maxPts;

    public double new21Game(int n, int k, int maxPts) {
        f = new double[k];
        this.n = n;
        this.k = k;
        this.maxPts = maxPts;
        return dfs(0);
    }

    private double dfs(int i) {
        if (i >= k) {
            return i <= n ? 1 : 0;
        }
        if (i == k - 1) {
            return Math.min(n - k + 1, maxPts) * 1.0 / maxPts;
        }
        if (f[i] != 0) {
            return f[i];
        }
        return f[i] = dfs(i + 1) + (dfs(i + 1) - dfs(i + maxPts + 1)) / maxPts;
    }
}
```

## Code (Python)

```python
class Solution:
    def new21Game(self, n: int, k: int, maxPts: int) -> float:
        @cache
        def dfs(i: int) -> float:
            if i >= k:
                return int(i <= n)
            if i == k - 1:
                return min(n - k + 1, maxPts) / maxPts
            return dfs(i + 1) + (dfs(i + 1) - dfs(i + maxPts + 1)) / maxPts

        return dfs(0)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
