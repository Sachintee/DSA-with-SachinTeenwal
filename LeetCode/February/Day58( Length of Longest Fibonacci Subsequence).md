--- ❤️ ---

# 🚀 _Day 58.  Length of Longest Fibonacci Subsequence_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/length-of-longest-fibonacci-subsequence/description/?envType=daily-question&envId=2025-02-27)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int lenLongestFibSubseq(vector<int>& arr) {
        int n = arr.size();
        int f[n][n];
        memset(f, 0, sizeof(f));
        unordered_map<int, int> d;
        for (int i = 0; i < n; ++i) {
            d[arr[i]] = i;
            for (int j = 0; j < i; ++j) {
                f[i][j] = 2;
            }
        }

        int ans = 0;
        for (int i = 2; i < n; ++i) {
            for (int j = 1; j < i; ++j) {
                int t = arr[i] - arr[j];
                auto it = d.find(t);
                if (it != d.end() && it->second < j) {
                    int k = it->second;
                    f[i][j] = max(f[i][j], f[j][k] + 1);
                    ans = max(ans, f[i][j]);
                }
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int lenLongestFibSubseq(int[] arr) {
        int n = arr.length;
        int[][] f = new int[n][n];
        Map<Integer, Integer> d = new HashMap<>();
        for (int i = 0; i < n; ++i) {
            d.put(arr[i], i);
            for (int j = 0; j < i; ++j) {
                f[i][j] = 2;
            }
        }
        int ans = 0;
        for (int i = 2; i < n; ++i) {
            for (int j = 1; j < i; ++j) {
                int t = arr[i] - arr[j];
                Integer k = d.get(t);
                if (k != null && k < j) {
                    f[i][j] = Math.max(f[i][j], f[j][k] + 1);
                    ans = Math.max(ans, f[i][j]);
                }
            }
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def lenLongestFibSubseq(self, arr: List[int]) -> int:
        n = len(arr)
        f = [[0] * n for _ in range(n)]
        d = {x: i for i, x in enumerate(arr)}
        for i in range(n):
            for j in range(i):
                f[i][j] = 2
        ans = 0
        for i in range(2, n):
            for j in range(1, i):
                t = arr[i] - arr[j]
                if t in d and (k := d[t]) < j:
                    f[i][j] = max(f[i][j], f[j][k] + 1)
                    ans = max(ans, f[i][j])
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
