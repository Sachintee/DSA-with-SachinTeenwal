--- ❤️ ---

# 🚀 _Day 35. Maximum Ascending Subarray Sum_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/maximum-ascending-subarray-sum/?envType=daily-question&envId=2025-02-04)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int maxAscendingSum(vector<int>& nums) {
        int ans = 0, t = 0;
        for (int i = 0; i < nums.size(); ++i) {
            if (i == 0 || nums[i] > nums[i - 1]) {
                t += nums[i];
                ans = max(ans, t);
            } else {
                t = nums[i];
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int maxAscendingSum(int[] nums) {
        int ans = 0, t = 0;
        for (int i = 0; i < nums.length; ++i) {
            if (i == 0 || nums[i] > nums[i - 1]) {
                t += nums[i];
                ans = Math.max(ans, t);
            } else {
                t = nums[i];
            }
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def maxAscendingSum(self, nums: List[int]) -> int:
        ans = t = 0
        for i, v in enumerate(nums):
            if i == 0 or v > nums[i - 1]:
                t += v
                ans = max(ans, t)
            else:
                t = v
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
