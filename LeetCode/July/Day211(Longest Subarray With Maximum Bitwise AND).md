--- ❤️ ---

# 🚀 _Day 211. Longest Subarray With Maximum Bitwise AND_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/longest-subarray-with-maximum-bitwise-and/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int longestSubarray(vector<int>& nums) {
        int mx = ranges::max(nums);
        int ans = 0, cnt = 0;
        for (int x : nums) {
            if (x == mx) {
                ans = max(ans, ++cnt);
            } else {
                cnt = 0;
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int longestSubarray(int[] nums) {
        int mx = Arrays.stream(nums).max().getAsInt();
        int ans = 0, cnt = 0;
        for (int x : nums) {
            if (x == mx) {
                ans = Math.max(ans, ++cnt);
            } else {
                cnt = 0;
            }
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def longestSubarray(self, nums: List[int]) -> int:
        mx = max(nums)
        ans = cnt = 0
        for x in nums:
            if x == mx:
                cnt += 1
                ans = max(ans, cnt)
            else:
                cnt = 0
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
