--- ❤️ ---

# 🚀 _Day 210. Smallest Subarrays With Maximum Bitwise OR_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/smallest-subarrays-with-maximum-bitwise-or/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    vector<int> smallestSubarrays(vector<int>& nums) {
        int n = nums.size();
        vector<int> f(32, -1);
        vector<int> ans(n);
        for (int i = n - 1; ~i; --i) {
            int t = 1;
            for (int j = 0; j < 32; ++j) {
                if ((nums[i] >> j) & 1) {
                    f[j] = i;
                } else if (f[j] != -1) {
                    t = max(t, f[j] - i + 1);
                }
            }
            ans[i] = t;
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int[] smallestSubarrays(int[] nums) {
        int n = nums.length;
        int[] ans = new int[n];
        int[] f = new int[32];
        Arrays.fill(f, -1);
        for (int i = n - 1; i >= 0; --i) {
            int t = 1;
            for (int j = 0; j < 32; ++j) {
                if (((nums[i] >> j) & 1) == 1) {
                    f[j] = i;
                } else if (f[j] != -1) {
                    t = Math.max(t, f[j] - i + 1);
                }
            }
            ans[i] = t;
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def smallestSubarrays(self, nums: List[int]) -> List[int]:
        n = len(nums)
        ans = [1] * n
        f = [-1] * 32
        for i in range(n - 1, -1, -1):
            t = 1
            for j in range(32):
                if (nums[i] >> j) & 1:
                    f[j] = i
                elif f[j] != -1:
                    t = max(t, f[j] - i + 1)
            ans[i] = t
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
