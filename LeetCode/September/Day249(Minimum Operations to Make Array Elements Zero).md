--- ❤️ ---

# 🚀 _Day 249. Minimum Operations to Make Array Elements Zero_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/minimum-operations-to-make-array-elements-zero/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    long long minOperations(vector<vector<int>>& queries) {
        auto f = [&](long long x) {
            long long res = 0;
            long long p = 1;
            int i = 1;
            while (p <= x) {
                long long cnt = min(p * 4 - 1, x) - p + 1;
                res += cnt * i;
                i++;
                p *= 4;
            }
            return res;
        };

        long long ans = 0;
        for (auto& q : queries) {
            int l = q[0], r = q[1];
            long long s = f(r) - f(l - 1);
            long long mx = f(r) - f(r - 1);
            ans += max((s + 1) / 2, mx);
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public long minOperations(int[][] queries) {
        long ans = 0;
        for (int[] q : queries) {
            int l = q[0], r = q[1];
            long s = f(r) - f(l - 1);
            long mx = f(r) - f(r - 1);
            ans += Math.max((s + 1) / 2, mx);
        }
        return ans;
    }

    private long f(long x) {
        long res = 0;
        long p = 1;
        int i = 1;
        while (p <= x) {
            long cnt = Math.min(p * 4 - 1, x) - p + 1;
            res += cnt * i;
            i++;
            p *= 4;
        }
        return res;
    }
}
```

## Code (Python3)

```python
class Solution:
    def minOperations(self, queries: List[List[int]]) -> int:
        def f(x: int) -> int:
            res = 0
            p = i = 1
            while p <= x:
                cnt = min(p * 4 - 1, x) - p + 1
                res += cnt * i
                i += 1
                p *= 4
            return res

        ans = 0
        for l, r in queries:
            s = f(r) - f(l - 1)
            mx = f(r) - f(r - 1)
            ans += max((s + 1) // 2, mx)
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
