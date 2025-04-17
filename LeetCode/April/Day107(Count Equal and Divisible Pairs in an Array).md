--- ❤️ ---

# 🚀 _Day 107. Count Equal and Divisible Pairs in an Array_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/count-equal-and-divisible-pairs-in-an-array/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int countPairs(vector<int>& nums, int k) {
        int ans = 0;
        for (int j = 1; j < nums.size(); ++j) {
            for (int i = 0; i < j; ++i) {
                ans += nums[i] == nums[j] && (i * j % k) == 0;
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int countPairs(int[] nums, int k) {
        int ans = 0;
        for (int j = 1; j < nums.length; ++j) {
            for (int i = 0; i < j; ++i) {
                ans += nums[i] == nums[j] && (i * j % k) == 0 ? 1 : 0;
            }
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def countPairs(self, nums: List[int], k: int) -> int:
        ans = 0
        for j, y in enumerate(nums):
            for i, x in enumerate(nums[:j]):
                ans += int(x == y and i * j % k == 0)
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
