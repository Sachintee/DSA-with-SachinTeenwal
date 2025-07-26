--- ❤️ ---

# 🚀 _Day 207. Maximize Subarrays After Removing One Conflicting Pair_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/maximize-subarrays-after-removing-one-conflicting-pair/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    long long maxSubarrays(int n, vector<vector<int>>& conflictingPairs) {
        vector<vector<int>> g(n + 1);
        for (auto& pair : conflictingPairs) {
            int a = pair[0], b = pair[1];
            if (a > b) {
                swap(a, b);
            }
            g[a].push_back(b);
        }

        vector<long long> cnt(n + 2, 0);
        long long ans = 0, add = 0;
        int b1 = n + 1, b2 = n + 1;

        for (int a = n; a > 0; --a) {
            for (int b : g[a]) {
                if (b < b1) {
                    b2 = b1;
                    b1 = b;
                } else if (b < b2) {
                    b2 = b;
                }
            }
            ans += b1 - a;
            cnt[b1] += b2 - b1;
            add = max(add, cnt[b1]);
        }

        ans += add;
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public long maxSubarrays(int n, int[][] conflictingPairs) {
        List<Integer>[] g = new List[n + 1];
        Arrays.setAll(g, k -> new ArrayList<>());
        for (int[] pair : conflictingPairs) {
            int a = pair[0], b = pair[1];
            if (a > b) {
                int c = a;
                a = b;
                b = c;
            }
            g[a].add(b);
        }
        long[] cnt = new long[n + 2];
        long ans = 0, add = 0;
        int b1 = n + 1, b2 = n + 1;
        for (int a = n; a > 0; --a) {
            for (int b : g[a]) {
                if (b < b1) {
                    b2 = b1;
                    b1 = b;
                } else if (b < b2) {
                    b2 = b;
                }
            }
            ans += b1 - a;
            cnt[b1] += b2 - b1;
            add = Math.max(add, cnt[b1]);
        }
        ans += add;
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def maxSubarrays(self, n: int, conflictingPairs: List[List[int]]) -> int:
        g = [[] for _ in range(n + 1)]
        for a, b in conflictingPairs:
            if a > b:
                a, b = b, a
            g[a].append(b)
        cnt = [0] * (n + 2)
        ans = add = 0
        b1 = b2 = n + 1
        for a in range(n, 0, -1):
            for b in g[a]:
                if b < b1:
                    b2, b1 = b1, b
                elif b < b2:
                    b2 = b
            ans += b1 - a
            cnt[b1] += b2 - b1
            add = max(add, cnt[b1])
        ans += add
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
