--- ❤️ ---

# 🚀 _Day 273. Find Triangular Sum of an Array_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/find-triangular-sum-of-an-array/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int triangularSum(vector<int>& nums) {
        for (int k = nums.size() - 1; k; --k) {
            for (int i = 0; i < k; ++i) {
                nums[i] = (nums[i] + nums[i + 1]) % 10;
            }
        }
        return nums[0];
    }
};
```

## Code (Java)

```java
class Solution:
    def triangularSum(self, nums: List[int]) -> int:
        for k in range(len(nums) - 1, 0, -1):
            for i in range(k):
                nums[i] = (nums[i] + nums[i + 1]) % 10
        return nums[0]
```

## Code (Python)

```python
class Solution:
    def triangularSum(self, nums: List[int]) -> int:
        for k in range(len(nums) - 1, 0, -1):
            for i in range(k):
                nums[i] = (nums[i] + nums[i + 1]) % 10
        return nums[0]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
