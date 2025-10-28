--- ❤️ ---

# 🚀 _Day 301. Make Array Elements Equal to Zero_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/make-array-elements-equal-to-zero/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int countValidSelections(vector<int>& nums) {
        int s = accumulate(nums.begin(), nums.end(), 0);
        int ans = 0, l = 0;
        for (int x : nums) {
            if (x) {
                l += x;
            } else if (l * 2 == s) {
                ans += 2;
            } else if (abs(l * 2 - s) <= 1) {
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
    public int countValidSelections(int[] nums) {
        int s = Arrays.stream(nums).sum();
        int ans = 0, l = 0;
        for (int x : nums) {
            if (x != 0) {
                l += x;
            } else if (l * 2 == s) {
                ans += 2;
            } else if (Math.abs(l * 2 - s) <= 1) {
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
    def countValidSelections(self, nums: List[int]) -> int:
        s = sum(nums)
        ans = l = 0
        for x in nums:
            if x:
                l += x
            elif l * 2 == s:
                ans += 2
            elif abs(l * 2 - s) == 1:
                ans += 1
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
