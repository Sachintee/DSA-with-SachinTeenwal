--- ❤️ ---

# 🚀 _Day 180. Number of Subsequences That Satisfy the Given Sum Condition_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/number-of-subsequences-that-satisfy-the-given-sum-condition/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int numSubseq(vector<int>& nums, int target) {
        sort(nums.begin(), nums.end());
        const int mod = 1e9 + 7;
        int n = nums.size();
        int f[n + 1];
        f[0] = 1;
        for (int i = 1; i <= n; ++i) {
            f[i] = (f[i - 1] * 2) % mod;
        }
        int ans = 0;
        for (int i = 0; i < n && nums[i] * 2 <= target; ++i) {
            int j = upper_bound(nums.begin() + i + 1, nums.end(), target - nums[i]) - nums.begin() - 1;
            ans = (ans + f[j - i]) % mod;
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int numSubseq(int[] nums, int target) {
        Arrays.sort(nums);
        final int mod = (int) 1e9 + 7;
        int n = nums.length;
        int[] f = new int[n + 1];
        f[0] = 1;
        for (int i = 1; i <= n; ++i) {
            f[i] = (f[i - 1] * 2) % mod;
        }
        int ans = 0;
        for (int i = 0; i < n && nums[i] * 2 <= target; ++i) {
            int j = search(nums, target - nums[i], i + 1) - 1;
            ans = (ans + f[j - i]) % mod;
        }
        return ans;
    }

    private int search(int[] nums, int x, int left) {
        int right = nums.length;
        while (left < right) {
            int mid = (left + right) >> 1;
            if (nums[mid] > x) {
                right = mid;
            } else {
                left = mid + 1;
            }
        }
        return left;
    }
}
```

## Code (Python)

```python
class Solution:
    def numSubseq(self, nums: List[int], target: int) -> int:
        mod = 10**9 + 7
        nums.sort()
        n = len(nums)
        f = [1] + [0] * n
        for i in range(1, n + 1):
            f[i] = f[i - 1] * 2 % mod
        ans = 0
        for i, x in enumerate(nums):
            if x * 2 > target:
                break
            j = bisect_right(nums, target - x, i + 1) - 1
            ans = (ans + f[j - i]) % mod
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
