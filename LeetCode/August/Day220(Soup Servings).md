--- ❤️ ---

# 🚀 _Day 220. Soup Servings_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/soup-servings/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    double soupServings(int n) {
        double f[200][200] = {0.0};
        auto dfs = [&](this auto&& dfs, int i, int j) -> double {
            if (i <= 0 && j <= 0) return 0.5;
            if (i <= 0) return 1;
            if (j <= 0) return 0;
            if (f[i][j] > 0) return f[i][j];
            double ans = 0.25 * (dfs(i - 4, j) + dfs(i - 3, j - 1) + dfs(i - 2, j - 2) + dfs(i - 1, j - 3));
            f[i][j] = ans;
            return ans;
        };
        return n > 4800 ? 1 : dfs((n + 24) / 25, (n + 24) / 25);
    }
};
```

## Code (Java)

```java
class Solution {
    private double[][] f = new double[200][200];

    public double soupServings(int n) {
        return n > 4800 ? 1 : dfs((n + 24) / 25, (n + 24) / 25);
    }

    private double dfs(int i, int j) {
        if (i <= 0 && j <= 0) {
            return 0.5;
        }
        if (i <= 0) {
            return 1.0;
        }
        if (j <= 0) {
            return 0;
        }
        if (f[i][j] > 0) {
            return f[i][j];
        }
        double ans
            = 0.25 * (dfs(i - 4, j) + dfs(i - 3, j - 1) + dfs(i - 2, j - 2) + dfs(i - 1, j - 3));
        f[i][j] = ans;
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def soupServings(self, n: int) -> float:
        @cache
        def dfs(i: int, j: int) -> float:
            if i <= 0 and j <= 0:
                return 0.5
            if i <= 0:
                return 1
            if j <= 0:
                return 0
            return 0.25 * (
                dfs(i - 4, j)
                + dfs(i - 3, j - 1)
                + dfs(i - 2, j - 2)
                + dfs(i - 1, j - 3)
            )

        return 1 if n > 4800 else dfs((n + 24) // 25, (n + 24) // 25)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
