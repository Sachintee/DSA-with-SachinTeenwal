---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Dynamic Programming
  - Arrays
---

# 🚀 _Day 81. Stickler Thief II_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/dynamic-programming-gfg-160/problem/house-robber-ii)  

## 💡 **Problem Description:**

You are given an array `arr[]` representing houses arranged in a **circular** fashion. Each house contains a certain value, and a thief aims to **maximize** the stolen amount while ensuring that **no two adjacent houses are robbed**.  


## Code(C++)
```cpp
class Solution {
public:
    int maxValue(vector<int>& nums) {
        int n = nums.size();
        if (n == 1) return nums[0];

        auto robRange = [&](int l, int r) {
            int prev2 = 0, prev1 = 0;
            for (int i = l; i <= r; i++) {
                int curr = max(prev1, prev2 + nums[i]);
                prev2 = prev1;
                prev1 = curr;
            }
            return prev1;
        };

        return max(robRange(0, n - 2), robRange(1, n - 1));
    }
};
```

## Code (Java)

```java
class Solution {
    public int maxValue(int[] nums) {
        int n = nums.length;
        if (n == 1) return nums[0];

        return Math.max(rob(nums, 0, n - 2), rob(nums, 1, n - 1));
    }

    private int rob(int[] nums, int l, int r) {
        int prev2 = 0, prev1 = 0;
        for (int i = l; i <= r; i++) {
            int curr = Math.max(prev1, prev2 + nums[i]);
            prev2 = prev1;
            prev1 = curr;
        }
        return prev1;
    }
}
```

## Code (Python)

```python
class Solution:
    def maxValue(self, nums):
        if len(nums) == 1:
            return nums[0]

        def rob(l, r):
            prev2 = prev1 = 0
            for i in range(l, r + 1):
                prev2, prev1 = prev1, max(prev1, prev2 + nums[i])
            return prev1

        return max(rob(0, len(nums) - 2), rob(1, len(nums) - 1))
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
