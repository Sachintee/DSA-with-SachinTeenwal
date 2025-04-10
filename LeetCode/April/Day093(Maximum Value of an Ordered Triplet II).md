--- ❤️ ---

# 🚀 _Day 93. Maximum Value of an Ordered Triplet II_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/maximum-value-of-an-ordered-triplet-ii/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    long long maximumTripletValue(vector<int>& nums) {
        long long ans = 0, mxDiff = 0;
        int mx = 0;
        for (int x : nums) {
            ans = max(ans, mxDiff * x);
            mxDiff = max(mxDiff, 1LL * mx - x);
            mx = max(mx, x);
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public long maximumTripletValue(int[] nums) {
        long ans = 0, mxDiff = 0;
        int mx = 0;
        for (int x : nums) {
            ans = Math.max(ans, mxDiff * x);
            mxDiff = Math.max(mxDiff, mx - x);
            mx = Math.max(mx, x);
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def maximumTripletValue(self, nums: List[int]) -> int:
        ans = mx = mx_diff = 0
        for x in nums:
            ans = max(ans, mx_diff * x)
            mx_diff = max(mx_diff, mx - x)
            mx = max(mx, x)
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
