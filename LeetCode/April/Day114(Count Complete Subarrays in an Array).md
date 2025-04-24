--- ❤️ ---

# 🚀 _Day 114. Count Complete Subarrays in an Array_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/count-complete-subarrays-in-an-array/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int countCompleteSubarrays(vector<int>& nums) {
        unordered_set<int> s(nums.begin(), nums.end());
        int cnt = s.size();
        int ans = 0, n = nums.size();
        for (int i = 0; i < n; ++i) {
            s.clear();
            for (int j = i; j < n; ++j) {
                s.insert(nums[j]);
                if (s.size() == cnt) {
                    ++ans;
                }
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int countCompleteSubarrays(int[] nums) {
        Set<Integer> s = new HashSet<>();
        for (int x : nums) {
            s.add(x);
        }
        int cnt = s.size();
        int ans = 0, n = nums.length;
        for (int i = 0; i < n; ++i) {
            s.clear();
            for (int j = i; j < n; ++j) {
                s.add(nums[j]);
                if (s.size() == cnt) {
                    ++ans;
                }
            }
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def countCompleteSubarrays(self, nums: List[int]) -> int:
        cnt = len(set(nums))
        ans, n = 0, len(nums)
        for i in range(n):
            s = set()
            for x in nums[i:]:
                s.add(x)
                if len(s) == cnt:
                    ans += 1
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
