--- ❤️ ---

# 🚀 _Day 169. Divide Array Into Arrays With Max Difference_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/divide-array-into-arrays-with-max-difference/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    vector<vector<int>> divideArray(vector<int>& nums, int k) {
        sort(nums.begin(), nums.end());
        vector<vector<int>> ans;
        int n = nums.size();
        for (int i = 0; i < n; i += 3) {
            vector<int> t = {nums[i], nums[i + 1], nums[i + 2]};
            if (t[2] - t[0] > k) {
                return {};
            }
            ans.emplace_back(t);
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int[][] divideArray(int[] nums, int k) {
        Arrays.sort(nums);
        int n = nums.length;
        int[][] ans = new int[n / 3][];
        for (int i = 0; i < n; i += 3) {
            int[] t = Arrays.copyOfRange(nums, i, i + 3);
            if (t[2] - t[0] > k) {
                return new int[][] {};
            }
            ans[i / 3] = t;
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def divideArray(self, nums: List[int], k: int) -> List[List[int]]:
        nums.sort()
        ans = []
        n = len(nums)
        for i in range(0, n, 3):
            t = nums[i : i + 3]
            if t[2] - t[0] > k:
                return []
            ans.append(t)
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
