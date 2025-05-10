--- ❤️ ---

# 🚀 _Day 130. Minimum Equal Sum of Two Arrays After Replacing Zeros_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/minimum-equal-sum-of-two-arrays-after-replacing-zeros/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    long long minSum(vector<int>& nums1, vector<int>& nums2) {
        long long s1 = 0, s2 = 0;
        bool hasZero = false;
        for (int x : nums1) {
            hasZero |= x == 0;
            s1 += max(x, 1);
        }
        for (int x : nums2) {
            s2 += max(x, 1);
        }
        if (s1 > s2) {
            return minSum(nums2, nums1);
        }
        if (s1 == s2) {
            return s1;
        }
        return hasZero ? s2 : -1;
    }
};
```

## Code (Java)

```java
class Solution {
    public long minSum(int[] nums1, int[] nums2) {
        long s1 = 0, s2 = 0;
        boolean hasZero = false;
        for (int x : nums1) {
            hasZero |= x == 0;
            s1 += Math.max(x, 1);
        }
        for (int x : nums2) {
            s2 += Math.max(x, 1);
        }
        if (s1 > s2) {
            return minSum(nums2, nums1);
        }
        if (s1 == s2) {
            return s1;
        }
        return hasZero ? s2 : -1;
    }
}
```

## Code (Python)

```python
class Solution:
    def minSum(self, nums1: List[int], nums2: List[int]) -> int:
        s1 = sum(nums1) + nums1.count(0)
        s2 = sum(nums2) + nums2.count(0)
        if s1 > s2:
            return self.minSum(nums2, nums1)
        if s1 == s2:
            return s1
        return -1 if nums1.count(0) == 0 else s2
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
