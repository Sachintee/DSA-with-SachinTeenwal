--- ❤️ ---

# 🚀 _Day 179. Find Subsequence of Length K With the Largest Sum_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/find-subsequence-of-length-k-with-the-largest-sum/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <ranges>

class Solution {
public:
    vector<int> maxSubsequence(vector<int>& nums, int k) {
        int n = nums.size();
        vector<int> idx(n);
        ranges::iota(idx, 0);
        ranges::sort(idx, [&](int i, int j) { return nums[i] < nums[j]; });
        ranges::sort(idx | views::drop(n - k));
        vector<int> ans(k);
        for (int i = n - k; i < n; ++i) {
            ans[i - (n - k)] = nums[idx[i]];
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int[] maxSubsequence(int[] nums, int k) {
        int n = nums.length;
        Integer[] idx = new Integer[n];
        Arrays.setAll(idx, i -> i);
        Arrays.sort(idx, (i, j) -> nums[i] - nums[j]);
        Arrays.sort(idx, n - k, n);
        int[] ans = new int[k];
        for (int i = n - k; i < n; ++i) {
            ans[i - (n - k)] = nums[idx[i]];
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def maxSubsequence(self, nums: List[int], k: int) -> List[int]:
        idx = sorted(range(len(nums)), key=lambda i: nums[i])[-k:]
        return [nums[i] for i in sorted(idx)]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
