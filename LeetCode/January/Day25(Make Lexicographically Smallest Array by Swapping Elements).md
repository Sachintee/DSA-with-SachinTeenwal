
# 🚀 _Day 25. Make Lexicographically Smallest Array by Swapping Elements_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/make-lexicographically-smallest-array-by-swapping-elements/submissions/1520129871/?envType=daily-question&envId=2025-01-25)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    vector<int> lexicographicallySmallestArray(vector<int>& nums, int limit) {
        int n = nums.size();
        vector<int> idx(n);
        iota(idx.begin(), idx.end(), 0);
        sort(idx.begin(), idx.end(), [&](int i, int j) {
            return nums[i] < nums[j];
        });
        vector<int> ans(n);
        for (int i = 0; i < n;) {
            int j = i + 1;
            while (j < n && nums[idx[j]] - nums[idx[j - 1]] <= limit) {
                ++j;
            }
            vector<int> t(idx.begin() + i, idx.begin() + j);
            sort(t.begin(), t.end());
            for (int k = i; k < j; ++k) {
                ans[t[k - i]] = nums[idx[k]];
            }
            i = j;
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int[] lexicographicallySmallestArray(int[] nums, int limit) {
        int n = nums.length;
        Integer[] idx = new Integer[n];
        for (int i = 0; i < n; ++i) {
            idx[i] = i;
        }
        Arrays.sort(idx, (i, j) -> nums[i] - nums[j]);
        int[] ans = new int[n];
        for (int i = 0; i < n;) {
            int j = i + 1;
            while (j < n && nums[idx[j]] - nums[idx[j - 1]] <= limit) {
                ++j;
            }
            Integer[] t = Arrays.copyOfRange(idx, i, j);
            Arrays.sort(t, (x, y) -> x - y);
            for (int k = i; k < j; ++k) {
                ans[t[k - i]] = nums[idx[k]];
            }
            i = j;
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def lexicographicallySmallestArray(self, nums: List[int], limit: int) -> List[int]:
        n = len(nums)
        arr = sorted(zip(nums, range(n)))
        ans = [0] * n
        i = 0
        while i < n:
            j = i + 1
            while j < n and arr[j][0] - arr[j - 1][0] <= limit:
                j += 1
            idx = sorted(k for _, k in arr[i:j])
            for k, (x, _) in zip(idx, arr[i:j]):
                ans[k] = x
            i = j
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
 <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>569</h4>
