--- ❤️ ---

# 🚀 _Day 96. Largest Divisible Subset_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/largest-divisible-subset/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    vector<int> largestDivisibleSubset(vector<int>& nums) {
        ranges::sort(nums);
        int n = nums.size();
        int f[n];
        int k = 0;
        for (int i = 0; i < n; ++i) {
            f[i] = 1;
            for (int j = 0; j < i; ++j) {
                if (nums[i] % nums[j] == 0) {
                    f[i] = max(f[i], f[j] + 1);
                }
            }
            if (f[k] < f[i]) {
                k = i;
            }
        }
        int m = f[k];
        vector<int> ans;
        for (int i = k; m > 0; --i) {
            if (nums[k] % nums[i] == 0 && f[i] == m) {
                ans.push_back(nums[i]);
                k = i;
                --m;
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public List<Integer> largestDivisibleSubset(int[] nums) {
        Arrays.sort(nums);
        int n = nums.length;
        int[] f = new int[n];
        Arrays.fill(f, 1);
        int k = 0;
        for (int i = 0; i < n; ++i) {
            for (int j = 0; j < i; ++j) {
                if (nums[i] % nums[j] == 0) {
                    f[i] = Math.max(f[i], f[j] + 1);
                }
            }
            if (f[k] < f[i]) {
                k = i;
            }
        }
        int m = f[k];
        List<Integer> ans = new ArrayList<>();
        for (int i = k; m > 0; --i) {
            if (nums[k] % nums[i] == 0 && f[i] == m) {
                ans.add(nums[i]);
                k = i;
                --m;
            }
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def largestDivisibleSubset(self, nums: List[int]) -> List[int]:
        nums.sort()
        n = len(nums)
        f = [1] * n
        k = 0
        for i in range(n):
            for j in range(i):
                if nums[i] % nums[j] == 0:
                    f[i] = max(f[i], f[j] + 1)
            if f[k] < f[i]:
                k = i
        m = f[k]
        i = k
        ans = []
        while m:
            if nums[k] % nums[i] == 0 and f[i] == m:
                ans.append(nums[i])
                k, m = i, m - 1
            i -= 1
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
