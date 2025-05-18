--- ❤️ ---

# 🚀 _Day 138. Painting a Grid With Three Different Colors_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/painting-a-grid-with-three-different-colors/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int colorTheGrid(int m, int n) {
        auto f1 = [&](int x) {
            int last = -1;
            for (int i = 0; i < m; ++i) {
                if (x % 3 == last) {
                    return false;
                }
                last = x % 3;
                x /= 3;
            }
            return true;
        };
        auto f2 = [&](int x, int y) {
            for (int i = 0; i < m; ++i) {
                if (x % 3 == y % 3) {
                    return false;
                }
                x /= 3;
                y /= 3;
            }
            return true;
        };

        const int mod = 1e9 + 7;
        int mx = pow(3, m);
        unordered_set<int> valid;
        vector<int> f(mx);
        for (int i = 0; i < mx; ++i) {
            if (f1(i)) {
                valid.insert(i);
                f[i] = 1;
            }
        }
        unordered_map<int, vector<int>> d;
        for (int i : valid) {
            for (int j : valid) {
                if (f2(i, j)) {
                    d[i].push_back(j);
                }
            }
        }
        for (int k = 1; k < n; ++k) {
            vector<int> g(mx);
            for (int i : valid) {
                for (int j : d[i]) {
                    g[i] = (g[i] + f[j]) % mod;
                }
            }
            f = move(g);
        }
        int ans = 0;
        for (int x : f) {
            ans = (ans + x) % mod;
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    private int m;

    public int colorTheGrid(int m, int n) {
        this.m = m;
        final int mod = (int) 1e9 + 7;
        int mx = (int) Math.pow(3, m);
        Set<Integer> valid = new HashSet<>();
        int[] f = new int[mx];
        for (int i = 0; i < mx; ++i) {
            if (f1(i)) {
                valid.add(i);
                f[i] = 1;
            }
        }
        Map<Integer, List<Integer>> d = new HashMap<>();
        for (int i : valid) {
            for (int j : valid) {
                if (f2(i, j)) {
                    d.computeIfAbsent(i, k -> new ArrayList<>()).add(j);
                }
            }
        }
        for (int k = 1; k < n; ++k) {
            int[] g = new int[mx];
            for (int i : valid) {
                for (int j : d.getOrDefault(i, List.of())) {
                    g[i] = (g[i] + f[j]) % mod;
                }
            }
            f = g;
        }
        int ans = 0;
        for (int x : f) {
            ans = (ans + x) % mod;
        }
        return ans;
    }

    private boolean f1(int x) {
        int last = -1;
        for (int i = 0; i < m; ++i) {
            if (x % 3 == last) {
                return false;
            }
            last = x % 3;
            x /= 3;
        }
        return true;
    }

    private boolean f2(int x, int y) {
        for (int i = 0; i < m; ++i) {
            if (x % 3 == y % 3) {
                return false;
            }
            x /= 3;
            y /= 3;
        }
        return true;
    }
}
```

## Code (Python)

```python
class Solution:
    def colorTheGrid(self, m: int, n: int) -> int:
        def f1(x: int) -> bool:
            last = -1
            for _ in range(m):
                if x % 3 == last:
                    return False
                last = x % 3
                x //= 3
            return True

        def f2(x: int, y: int) -> bool:
            for _ in range(m):
                if x % 3 == y % 3:
                    return False
                x, y = x // 3, y // 3
            return True

        mod = 10**9 + 7
        mx = 3**m
        valid = {i for i in range(mx) if f1(i)}
        d = defaultdict(list)
        for x in valid:
            for y in valid:
                if f2(x, y):
                    d[x].append(y)
        f = [int(i in valid) for i in range(mx)]
        for _ in range(n - 1):
            g = [0] * mx
            for i in valid:
                for j in d[i]:
                    g[i] = (g[i] + f[j]) % mod
            f = g
        return sum(f) % mod
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
