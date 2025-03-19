--- ❤️ ---

# 🚀 _Day 78.  Minimum Operations to Make Binary Array Elements Equal to One I_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/minimum-operations-to-make-binary-array-elements-equal-to-one-i/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int minOperations(vector<int>& nums) {
        int ans = 0;
        int n = nums.size();
        for (int i = 0; i < n; ++i) {
            if (nums[i] == 0) {
                if (i + 2 >= n) {
                    return -1;
                }
                nums[i + 1] ^= 1;
                nums[i + 2] ^= 1;
                ++ans;
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int minOperations(int[] nums) {
        int ans = 0;
        int n = nums.length;
        for (int i = 0; i < n; ++i) {
            if (nums[i] == 0) {
                if (i + 2 >= n) {
                    return -1;
                }
                nums[i + 1] ^= 1;
                nums[i + 2] ^= 1;
                ++ans;
            }
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def minOperations(self, nums: List[int]) -> int:
        ans = 0
        for i, x in enumerate(nums):
            if x == 0:
                if i + 2 >= len(nums):
                    return -1
                nums[i + 1] ^= 1
                nums[i + 2] ^= 1
                ans += 1
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
