--- ❤️ ---

# 🚀 _Day 140. Zero Array Transformation I_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/zero-array-transformation-i/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    bool isZeroArray(vector<int>& nums, vector<vector<int>>& queries) {
        int n = nums.size();
        int d[n + 1];
        memset(d, 0, sizeof(d));
        for (const auto& q : queries) {
            int l = q[0], r = q[1];
            ++d[l];
            --d[r + 1];
        }
        for (int i = 0, s = 0; i < n; ++i) {
            s += d[i];
            if (nums[i] > s) {
                return false;
            }
        }
        return true;
    }
};
```

## Code (Java)

```java
class Solution {
    public boolean isZeroArray(int[] nums, int[][] queries) {
        int n = nums.length;
        int[] d = new int[n + 1];
        for (var q : queries) {
            int l = q[0], r = q[1];
            ++d[l];
            --d[r + 1];
        }
        for (int i = 0, s = 0; i < n; ++i) {
            s += d[i];
            if (nums[i] > s) {
                return false;
            }
        }
        return true;
    }
}
```

## Code (Python)

```python
class Solution:
    def isZeroArray(self, nums: List[int], queries: List[List[int]]) -> bool:
        d = [0] * (len(nums) + 1)
        for l, r in queries:
            d[l] += 1
            d[r + 1] -= 1
        s = 0
        for x, y in zip(nums, d):
            s += y
            if x > s:
                return False
        return True
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
