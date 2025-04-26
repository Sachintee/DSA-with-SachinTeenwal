--- ❤️ ---

# 🚀 _Day 116. Count Subarrays With Fixed Bounds_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/count-subarrays-with-fixed-bounds/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    long long countSubarrays(vector<int>& nums, int minK, int maxK) {
        long long ans = 0;
        int j1 = -1, j2 = -1, k = -1;
        for (int i = 0; i < static_cast<int>(nums.size()); ++i) {
            if (nums[i] < minK || nums[i] > maxK) {
                k = i;
            }
            if (nums[i] == minK) {
                j1 = i;
            }
            if (nums[i] == maxK) {
                j2 = i;
            }
            ans += max(0, min(j1, j2) - k);
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public long countSubarrays(int[] nums, int minK, int maxK) {
        long ans = 0;
        int j1 = -1, j2 = -1, k = -1;
        for (int i = 0; i < nums.length; ++i) {
            if (nums[i] < minK || nums[i] > maxK) {
                k = i;
            }
            if (nums[i] == minK) {
                j1 = i;
            }
            if (nums[i] == maxK) {
                j2 = i;
            }
            ans += Math.max(0, Math.min(j1, j2) - k);
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def countSubarrays(self, nums: List[int], minK: int, maxK: int) -> int:
        j1 = j2 = k = -1
        ans = 0
        for i, v in enumerate(nums):
            if v < minK or v > maxK:
                k = i
            if v == minK:
                j1 = i
            if v == maxK:
                j2 = i
            ans += max(0, min(j1, j2) - k)
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
