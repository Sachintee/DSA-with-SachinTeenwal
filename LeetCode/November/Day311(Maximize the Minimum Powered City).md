--- ❤️ ---

# 🚀 _Day 311. Maximize the Minimum Powered City_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/maximize-the-minimum-powered-city)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    long long maxPower(vector<int>& stations, int r, int k) {
        int n = stations.size();
        long long d[n + 1];
        memset(d, 0, sizeof d);
        for (int i = 0; i < n; ++i) {
            int left = max(0, i - r), right = min(i + r, n - 1);
            d[left] += stations[i];
            d[right + 1] -= stations[i];
        }
        long long s[n + 1];
        s[0] = d[0];
        for (int i = 1; i < n + 1; ++i) {
            s[i] = s[i - 1] + d[i];
        }
        auto check = [&](long long x, int k) {
            memset(d, 0, sizeof d);
            long long t = 0;
            for (int i = 0; i < n; ++i) {
                t += d[i];
                long long dist = x - (s[i] + t);
                if (dist > 0) {
                    if (k < dist) {
                        return false;
                    }
                    k -= dist;
                    int j = min(i + r, n - 1);
                    int left = max(0, j - r), right = min(j + r, n - 1);
                    d[left] += dist;
                    d[right + 1] -= dist;
                    t += dist;
                }
            }
            return true;
        };
        long long left = 0, right = 1e12;
        while (left < right) {
            long long mid = (left + right + 1) >> 1;
            if (check(mid, k)) {
                left = mid;
            } else {
                right = mid - 1;
            }
        }
        return left;
    }
};
```

## Code (Java)

```java
class Solution {
    private long[] s;
    private long[] d;
    private int n;

    public long maxPower(int[] stations, int r, int k) {
        n = stations.length;
        d = new long[n + 1];
        s = new long[n + 1];
        for (int i = 0; i < n; ++i) {
            int left = Math.max(0, i - r), right = Math.min(i + r, n - 1);
            d[left] += stations[i];
            d[right + 1] -= stations[i];
        }
        s[0] = d[0];
        for (int i = 1; i < n + 1; ++i) {
            s[i] = s[i - 1] + d[i];
        }
        long left = 0, right = 1l << 40;
        while (left < right) {
            long mid = (left + right + 1) >>> 1;
            if (check(mid, r, k)) {
                left = mid;
            } else {
                right = mid - 1;
            }
        }
        return left;
    }

    private boolean check(long x, int r, int k) {
        Arrays.fill(d, 0);
        long t = 0;
        for (int i = 0; i < n; ++i) {
            t += d[i];
            long dist = x - (s[i] + t);
            if (dist > 0) {
                if (k < dist) {
                    return false;
                }
                k -= dist;
                int j = Math.min(i + r, n - 1);
                int left = Math.max(0, j - r), right = Math.min(j + r, n - 1);
                d[left] += dist;
                d[right + 1] -= dist;
                t += dist;
            }
        }
        return true;
    }
}
```

## Code (Python)

```python
class Solution:
    def maxPower(self, stations: List[int], r: int, k: int) -> int:
        def check(x, k):
            d = [0] * (n + 1)
            t = 0
            for i in range(n):
                t += d[i]
                dist = x - (s[i] + t)
                if dist > 0:
                    if k < dist:
                        return False
                    k -= dist
                    j = min(i + r, n - 1)
                    left, right = max(0, j - r), min(j + r, n - 1)
                    d[left] += dist
                    d[right + 1] -= dist
                    t += dist
            return True

        n = len(stations)
        d = [0] * (n + 1)
        for i, v in enumerate(stations):
            left, right = max(0, i - r), min(i + r, n - 1)
            d[left] += v
            d[right + 1] -= v
        s = list(accumulate(d))
        left, right = 0, 1 << 40
        while left < right:
            mid = (left + right + 1) >> 1
            if check(mid, k):
                left = mid
            else:
                right = mid - 1
        return left
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
