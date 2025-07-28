--- ❤️ ---

# 🚀 _Day 209. Count Number of Maximum Bitwise-OR Subsets_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/count-number-of-maximum-bitwise-or-subsets/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int countMaxOrSubsets(vector<int>& nums) {
        int ans = 0;
        int mx = accumulate(nums.begin(), nums.end(), 0, bit_or<int>());
        auto dfs = [&](this auto&& dfs, int i, int t) {
            if (i == nums.size()) {
                if (t == mx) {
                    ans++;
                }
                return;
            }
            dfs(i + 1, t);
            dfs(i + 1, t | nums[i]);
        };
        dfs(0, 0);
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    private int mx;
    private int ans;
    private int[] nums;

    public int countMaxOrSubsets(int[] nums) {
        mx = 0;
        for (int x : nums) {
            mx |= x;
        }
        this.nums = nums;
        dfs(0, 0);
        return ans;
    }

    private void dfs(int i, int t) {
        if (i == nums.length) {
            if (t == mx) {
                ++ans;
            }
            return;
        }
        dfs(i + 1, t);
        dfs(i + 1, t | nums[i]);
    }
}
```

## Code (Python)

```python
class Solution:
    def countMaxOrSubsets(self, nums: List[int]) -> int:
        def dfs(i, t):
            nonlocal ans, mx
            if i == len(nums):
                if t == mx:
                    ans += 1
                return
            dfs(i + 1, t)
            dfs(i + 1, t | nums[i])

        ans = 0
        mx = reduce(lambda x, y: x | y, nums)
        dfs(0, 0)
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
