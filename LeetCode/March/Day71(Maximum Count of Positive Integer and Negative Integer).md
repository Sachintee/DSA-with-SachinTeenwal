--- ❤️ ---

# 🚀 _Day 71. Maximum Count of Positive Integer and Negative Integer_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/maximum-count-of-positive-integer-and-negative-integer/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int maximumCount(vector<int>& nums) {
        int a = 0, b = 0;
        for (int x : nums) {
            if (x > 0) {
                ++a;
            } else if (x < 0) {
                ++b;
            }
        }
        return max(a, b);
    }
};
```

## Code (Java)

```java
class Solution {
    public int maximumCount(int[] nums) {
        int a = 0, b = 0;
        for (int x : nums) {
            if (x > 0) {
                ++a;
            } else if (x < 0) {
                ++b;
            }
        }
        return Math.max(a, b);
    }
}
```

## Code (Python)

```python
class Solution:
    def maximumCount(self, nums: List[int]) -> int:
        a = sum(x > 0 for x in nums)
        b = sum(x < 0 for x in nums)
        return max(a, b)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
