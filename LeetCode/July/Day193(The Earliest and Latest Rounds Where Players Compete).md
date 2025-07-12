--- ❤️ ---

# 🚀 _Day 193. The Earliest and Latest Rounds Where Players Compete_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/the-earliest-and-latest-rounds-where-players-compete/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
int f[30][30][31];
class Solution {
public:
    vector<int> earliestAndLatest(int n, int firstPlayer, int secondPlayer) {
        return dfs(firstPlayer - 1, secondPlayer - 1, n);
    }

private:
    vector<int> dfs(int l, int r, int n) {
        if (f[l][r][n] != 0) {
            return decode(f[l][r][n]);
        }
        if (l + r == n - 1) {
            f[l][r][n] = encode(1, 1);
            return {1, 1};
        }

        int min = INT_MAX, max = INT_MIN;
        int m = n >> 1;

        for (int i = 0; i < (1 << m); i++) {
            vector<bool> win(n, false);
            for (int j = 0; j < m; j++) {
                if ((i >> j) & 1) {
                    win[j] = true;
                } else {
                    win[n - 1 - j] = true;
                }
            }
            if (n & 1) {
                win[m] = true;
            }

            win[n - 1 - l] = false;
            win[n - 1 - r] = false;
            win[l] = true;
            win[r] = true;

            int a = 0, b = 0, c = 0;
            for (int j = 0; j < n; j++) {
                if (j == l) a = c;
                if (j == r) b = c;
                if (win[j]) c++;
            }

            vector<int> t = dfs(a, b, c);
            min = std::min(min, t[0] + 1);
            max = std::max(max, t[1] + 1);
        }

        f[l][r][n] = encode(min, max);
        return {min, max};
    }

    int encode(int x, int y) {
        return (x << 8) | y;
    }

    vector<int> decode(int val) {
        return {val >> 8, val & 255};
    }
};
```

## Code (Java)

```java
class Solution {
    static int[][][] f = new int[30][30][31];

    public int[] earliestAndLatest(int n, int firstPlayer, int secondPlayer) {
        return dfs(firstPlayer - 1, secondPlayer - 1, n);
    }

    private int[] dfs(int l, int r, int n) {
        if (f[l][r][n] != 0) {
            return decode(f[l][r][n]);
        }
        if (l + r == n - 1) {
            f[l][r][n] = encode(1, 1);
            return new int[] {1, 1};
        }
        int min = Integer.MAX_VALUE, max = Integer.MIN_VALUE;
        int m = n >> 1;
        for (int i = 0; i < (1 << m); i++) {
            boolean[] win = new boolean[n];
            for (int j = 0; j < m; j++) {
                if (((i >> j) & 1) == 1) {
                    win[j] = true;
                } else {
                    win[n - 1 - j] = true;
                }
            }
            if ((n & 1) == 1) {
                win[m] = true;
            }
            win[n - 1 - l] = win[n - 1 - r] = false;
            win[l] = win[r] = true;
            int a = 0, b = 0, c = 0;
            for (int j = 0; j < n; j++) {
                if (j == l) {
                    a = c;
                }
                if (j == r) {
                    b = c;
                }
                if (win[j]) {
                    c++;
                }
            }
            int[] t = dfs(a, b, c);
            min = Math.min(min, t[0] + 1);
            max = Math.max(max, t[1] + 1);
        }
        f[l][r][n] = encode(min, max);
        return new int[] {min, max};
    }

    private int encode(int x, int y) {
        return (x << 8) | y;
    }

    private int[] decode(int val) {
        return new int[] {val >> 8, val & 255};
    }
}
```

## Code (Python)

```python
@cache
def dfs(l: int, r: int, n: int):
    if l + r == n - 1:
        return [1, 1]
    res = [inf, -inf]
    m = n >> 1
    for i in range(1 << m):
        win = [False] * n
        for j in range(m):
            if i >> j & 1:
                win[j] = True
            else:
                win[n - 1 - j] = True
        if n & 1:
            win[m] = True
        win[n - 1 - l] = win[n - 1 - r] = False
        win[l] = win[r] = True
        a = b = c = 0
        for j in range(n):
            if j == l:
                a = c
            if j == r:
                b = c
            if win[j]:
                c += 1
        x, y = dfs(a, b, c)
        res[0] = min(res[0], x + 1)
        res[1] = max(res[1], y + 1)
    return res


class Solution:
    def earliestAndLatest(
        self, n: int, firstPlayer: int, secondPlayer: int
    ) -> List[int]:
        return dfs(firstPlayer - 1, secondPlayer - 1, n)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
