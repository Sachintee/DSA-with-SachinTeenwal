--- ❤️ ---

# 🚀 _Day 291. Maximum Number of Distinct Elements After Operations_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/maximum-number-of-distinct-elements-after-operations/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int maxDistinctElements(vector<int>& nums, int k) {
        ranges::sort(nums);
        int ans = 0, pre = INT_MIN;
        for (int x : nums) {
            int cur = min(x + k, max(x - k, pre + 1));
            if (cur > pre) {
                ++ans;
                pre = cur;
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int maxDistinctElements(int[] nums, int k) {
        Arrays.sort(nums);
        int n = nums.length;
        int ans = 0, pre = Integer.MIN_VALUE;
        for (int x : nums) {
            int cur = Math.min(x + k, Math.max(x - k, pre + 1));
            if (cur > pre) {
                ++ans;
                pre = cur;
            }
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def maxDistinctElements(self, nums: List[int], k: int) -> int:
        nums.sort()
        ans = 0
        pre = -inf
        for x in nums:
            cur = min(x + k, max(x - k, pre + 1))
            if cur > pre:
                ans += 1
                pre = cur
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
