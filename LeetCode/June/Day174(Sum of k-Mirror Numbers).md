--- ❤️ ---

# 🚀 _Day 174. Sum of k-Mirror Numbers_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/sum-of-k-mirror-numbers/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    long long kMirror(int k, int n) {
        long long ans = 0;
        for (int l = 1;; ++l) {
            int x = pow(10, (l - 1) / 2);
            int y = pow(10, (l + 1) / 2);
            for (int i = x; i < y; ++i) {
                long long v = i;
                int j = (l % 2 == 0) ? i : i / 10;
                while (j > 0) {
                    v = v * 10 + j % 10;
                    j /= 10;
                }
                if (check(v, k)) {
                    ans += v;
                    if (--n == 0) {
                        return ans;
                    }
                }
            }
        }
    }

private:
    bool check(long long x, int k) {
        vector<int> s;
        while (x > 0) {
            s.push_back(x % k);
            x /= k;
        }
        for (int i = 0, j = s.size() - 1; i < j; ++i, --j) {
            if (s[i] != s[j]) {
                return false;
            }
        }
        return true;
    }
};
```

## Code (Java)

```java
class Solution {
    public long kMirror(int k, int n) {
        long ans = 0;
        for (int l = 1;; l++) {
            int x = (int) Math.pow(10, (l - 1) / 2);
            int y = (int) Math.pow(10, (l + 1) / 2);
            for (int i = x; i < y; i++) {
                long v = i;
                int j = (l % 2 == 0) ? i : i / 10;
                while (j > 0) {
                    v = v * 10 + j % 10;
                    j /= 10;
                }
                if (check(v, k)) {
                    ans += v;
                    n--;
                    if (n == 0) {
                        return ans;
                    }
                }
            }
        }
    }

    private boolean check(long x, int k) {
        List<Integer> s = new ArrayList<>();
        while (x > 0) {
            s.add((int) (x % k));
            x /= k;
        }
        for (int i = 0, j = s.size() - 1; i < j; ++i, --j) {
            if (!s.get(i).equals(s.get(j))) {
                return false;
            }
        }
        return true;
    }
}
```

## Code (Python)

```python
class Solution:
    def kMirror(self, k: int, n: int) -> int:
        def check(x: int, k: int) -> bool:
            s = []
            while x:
                s.append(x % k)
                x //= k
            return s == s[::-1]

        ans = 0
        for l in count(1):
            x = 10 ** ((l - 1) // 2)
            y = 10 ** ((l + 1) // 2)
            for i in range(x, y):
                v = i
                j = i if l % 2 == 0 else i // 10
                while j > 0:
                    v = v * 10 + j % 10
                    j //= 10
                if check(v, k):
                    ans += v
                    n -= 1
                    if n == 0:
                        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
