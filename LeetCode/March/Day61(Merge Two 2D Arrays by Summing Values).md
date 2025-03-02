--- ❤️ ---

# 🚀 _Day 61. Merge Two 2D Arrays by Summing Values_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/merge-two-2d-arrays-by-summing-values/description/?envType=daily-question&envId=2025-03-02)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    vector<vector<int>> mergeArrays(vector<vector<int>>& nums1, vector<vector<int>>& nums2) {
        int cnt[1001]{};
        for (auto& x : nums1) {
            cnt[x[0]] += x[1];
        }
        for (auto& x : nums2) {
            cnt[x[0]] += x[1];
        }
        vector<vector<int>> ans;
        for (int i = 0; i < 1001; ++i) {
            if (cnt[i]) {
                ans.push_back({i, cnt[i]});
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int[][] mergeArrays(int[][] nums1, int[][] nums2) {
        int[] cnt = new int[1001];
        for (var x : nums1) {
            cnt[x[0]] += x[1];
        }
        for (var x : nums2) {
            cnt[x[0]] += x[1];
        }
        int n = 0;
        for (int i = 0; i < 1001; ++i) {
            if (cnt[i] > 0) {
                ++n;
            }
        }
        int[][] ans = new int[n][2];
        for (int i = 0, j = 0; i < 1001; ++i) {
            if (cnt[i] > 0) {
                ans[j++] = new int[] {i, cnt[i]};
            }
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def mergeArrays(
        self, nums1: List[List[int]], nums2: List[List[int]]
    ) -> List[List[int]]:
        cnt = Counter()
        for i, v in nums1 + nums2:
            cnt[i] += v
        return sorted(cnt.items())
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
