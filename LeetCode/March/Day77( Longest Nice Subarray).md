--- ❤️ ---

# 🚀 _Day 77.  Longest Nice Subarray_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/longest-nice-subarray/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int longestNiceSubarray(vector<int>& nums) {
        int ans = 0, mask = 0;
        for (int l = 0, r = 0; r < nums.size(); ++r) {
            while (mask & nums[r]) {
                mask ^= nums[l++];
            }
            mask |= nums[r];
            ans = max(ans, r - l + 1);
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int longestNiceSubarray(int[] nums) {
        int ans = 0, mask = 0;
        for (int l = 0, r = 0; r < nums.length; ++r) {
            while ((mask & nums[r]) != 0) {
                mask ^= nums[l++];
            }
            mask |= nums[r];
            ans = Math.max(ans, r - l + 1);
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def longestNiceSubarray(self, nums: List[int]) -> int:
        ans = mask = l = 0
        for r, x in enumerate(nums):
            while mask & x:
                mask ^= nums[l]
                l += 1
            mask |= x
            ans = max(ans, r - l + 1)
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
