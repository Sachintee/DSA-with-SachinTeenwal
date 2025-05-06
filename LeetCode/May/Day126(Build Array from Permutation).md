--- ❤️ ---

# 🚀 _Day 126. Build Array from Permutation_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/build-array-from-permutation/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    vector<int> buildArray(vector<int>& nums) {
        vector<int> ans;
        for (int& num : nums) {
            ans.push_back(nums[num]);
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int[] buildArray(int[] nums) {
        int[] ans = new int[nums.length];
        for (int i = 0; i < nums.length; ++i) {
            ans[i] = nums[nums[i]];
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def buildArray(self, nums: List[int]) -> List[int]:
        return [nums[num] for num in nums]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
