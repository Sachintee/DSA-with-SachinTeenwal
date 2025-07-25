--- ❤️ ---

# 🚀 _Day 206. Maximum Unique Subarray Sum After Deletion_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/maximum-unique-subarray-sum-after-deletion/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int maxSum(vector<int>& nums) {
        int mx = ranges::max(nums);
        if (mx <= 0) {
            return mx;
        }
        unordered_set<int> s;
        int ans = 0;
        for (int x : nums) {
            if (x < 0 || s.contains(x)) {
                continue;
            }
            ans += x;
            s.insert(x);
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int maxSum(int[] nums) {
        int mx = Arrays.stream(nums).max().getAsInt();
        if (mx <= 0) {
            return mx;
        }
        boolean[] s = new boolean[201];
        int ans = 0;
        for (int x : nums) {
            if (x < 0 || s[x]) {
                continue;
            }
            ans += x;
            s[x] = true;
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def maxSum(self, nums: List[int]) -> int:
        mx = max(nums)
        if mx <= 0:
            return mx
        ans = 0
        s = set()
        for x in nums:
            if x < 0 or x in s:
                continue
            ans += x
            s.add(x)
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
