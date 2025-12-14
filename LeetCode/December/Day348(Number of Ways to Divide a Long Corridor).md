--- ❤️ ---

# 🚀 _Day 348. Number of Ways to Divide a Long Corridor_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/number-of-ways-to-divide-a-long-corridor/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int numberOfWays(string corridor) {
        int n = corridor.size();
        int f[n][3];
        memset(f, -1, sizeof(f));
        const int mod = 1e9 + 7;
        auto dfs = [&](this auto&& dfs, int i, int k) -> int {
            if (i >= n) {
                return k == 2;
            }
            if (f[i][k] != -1) {
                return f[i][k];
            }
            k += corridor[i] == 'S';
            if (k > 2) {
                return 0;
            }
            f[i][k] = dfs(i + 1, k);
            if (k == 2) {
                f[i][k] = (f[i][k] + dfs(i + 1, 0)) % mod;
            }
            return f[i][k];
        };
        return dfs(0, 0);
    }
};
```

## Code (Java)

```java

```

## Code (Python)

```python

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
