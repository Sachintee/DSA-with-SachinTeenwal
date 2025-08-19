--- ❤️ ---

# 🚀 _Day 231. Number of Zero-Filled Subarrays_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/number-of-zero-filled-subarrays/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    long long zeroFilledSubarray(vector<int>& nums) {
        long long ans = 0;
        int cnt = 0;
        for (int x : nums) {
            if (x == 0) {
                ans += ++cnt;
            } else {
                cnt = 0;
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public long zeroFilledSubarray(int[] nums) {
        long ans = 0;
        int cnt = 0;
        for (int x : nums) {
            if (x == 0) {
                ans += ++cnt;
            } else {
                cnt = 0;
            }
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def zeroFilledSubarray(self, nums: List[int]) -> int:
        ans = cnt = 0
        for x in nums:
            if x == 0:
                cnt += 1
                ans += cnt
            else:
                cnt = 0
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
