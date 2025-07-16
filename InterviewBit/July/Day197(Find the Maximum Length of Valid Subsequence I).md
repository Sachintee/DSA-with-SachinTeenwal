--- ❤️ ---

# 🚀 _Day 197. Find the Maximum Length of Valid Subsequence I_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/find-the-maximum-length-of-valid-subsequence-i/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int maximumLength(vector<int>& nums) {
        int k = 2;
        int f[k][k];
        memset(f, 0, sizeof(f));
        int ans = 0;
        for (int x : nums) {
            x %= k;
            for (int j = 0; j < k; ++j) {
                int y = (j - x + k) % k;
                f[x][y] = f[y][x] + 1;
                ans = max(ans, f[x][y]);
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int maximumLength(int[] nums) {
        int k = 2;
        int[][] f = new int[k][k];
        int ans = 0;
        for (int x : nums) {
            x %= k;
            for (int j = 0; j < k; ++j) {
                int y = (j - x + k) % k;
                f[x][y] = f[y][x] + 1;
                ans = Math.max(ans, f[x][y]);
            }
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def maximumLength(self, nums: List[int]) -> int:
        k = 2
        f = [[0] * k for _ in range(k)]
        ans = 0
        for x in nums:
            x %= k
            for j in range(k):
                y = (j - x + k) % k
                f[x][y] = f[y][x] + 1
                ans = max(ans, f[x][y])
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
