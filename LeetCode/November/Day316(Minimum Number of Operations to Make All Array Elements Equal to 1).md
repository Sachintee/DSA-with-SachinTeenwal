--- ❤️ ---

# 🚀 _Day 316. Minimum Number of Operations to Make All Array Elements Equal to 1_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/minimum-number-of-operations-to-make-all-array-elements-equal-to-1/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int minOperations(vector<int>& nums) {
        int n = nums.size();
        int cnt = 0;
        for (int x : nums) {
            if (x == 1) {
                ++cnt;
            }
        }
        if (cnt) {
            return n - cnt;
        }
        int mi = n + 1;
        for (int i = 0; i < n; ++i) {
            int g = 0;
            for (int j = i; j < n; ++j) {
                g = gcd(g, nums[j]);
                if (g == 1) {
                    mi = min(mi, j - i + 1);
                }
            }
        }
        return mi > n ? -1 : n - 1 + mi - 1;
    }
};
```

## Code (Java)

```java
class Solution {
    public int minOperations(int[] nums) {
        int n = nums.length;
        int cnt = 0;
        for (int x : nums) {
            if (x == 1) {
                ++cnt;
            }
        }
        if (cnt > 0) {
            return n - cnt;
        }
        int mi = n + 1;
        for (int i = 0; i < n; ++i) {
            int g = 0;
            for (int j = i; j < n; ++j) {
                g = gcd(g, nums[j]);
                if (g == 1) {
                    mi = Math.min(mi, j - i + 1);
                }
            }
        }
        return mi > n ? -1 : n - 1 + mi - 1;
    }

    private int gcd(int a, int b) {
        return b == 0 ? a : gcd(b, a % b);
    }
}
```

## Code (Python)

```python
class Solution:
    def minOperations(self, nums: List[int]) -> int:
        n = len(nums)
        cnt = nums.count(1)
        if cnt:
            return n - cnt
        mi = n + 1
        for i in range(n):
            g = 0
            for j in range(i, n):
                g = gcd(g, nums[j])
                if g == 1:
                    mi = min(mi, j - i + 1)
        return -1 if mi > n else n - 1 + mi - 1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
