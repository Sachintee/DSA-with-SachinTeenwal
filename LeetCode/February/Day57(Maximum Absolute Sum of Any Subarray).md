--- ❤️ ---

# 🚀 _Day 57. Maximum Absolute Sum of Any Subarray_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/maximum-absolute-sum-of-any-subarray/description/?envType=daily-question&envId=2025-02-26)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int maxAbsoluteSum(vector<int>& nums) {
        int f = 0, g = 0;
        int ans = 0;
        for (int& x : nums) {
            f = max(f, 0) + x;
            g = min(g, 0) + x;
            ans = max({ans, f, abs(g)});
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int maxAbsoluteSum(int[] nums) {
        int f = 0, g = 0;
        int ans = 0;
        for (int x : nums) {
            f = Math.max(f, 0) + x;
            g = Math.min(g, 0) + x;
            ans = Math.max(ans, Math.max(f, Math.abs(g)));
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def maxAbsoluteSum(self, nums: List[int]) -> int:
        f = g = 0
        ans = 0
        for x in nums:
            f = max(f, 0) + x
            g = min(g, 0) + x
            ans = max(ans, f, abs(g))
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
