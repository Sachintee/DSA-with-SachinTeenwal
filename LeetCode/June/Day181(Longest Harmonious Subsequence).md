--- ❤️ ---

# 🚀 _Day 181. Longest Harmonious Subsequence_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/longest-harmonious-subsequence/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int findLHS(vector<int>& nums) {
        unordered_map<int, int> cnt;
        for (int x : nums) {
            ++cnt[x];
        }
        int ans = 0;
        for (auto& [x, c] : cnt) {
            if (cnt.contains(x + 1)) {
                ans = max(ans, c + cnt[x + 1]);
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int findLHS(int[] nums) {
        Map<Integer, Integer> cnt = new HashMap<>();
        for (int x : nums) {
            cnt.merge(x, 1, Integer::sum);
        }
        int ans = 0;
        for (var e : cnt.entrySet()) {
            int x = e.getKey(), c = e.getValue();
            if (cnt.containsKey(x + 1)) {
                ans = Math.max(ans, c + cnt.get(x + 1));
            }
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def findLHS(self, nums: List[int]) -> int:
        cnt = Counter(nums)
        return max((c + cnt[x + 1] for x, c in cnt.items() if cnt[x + 1]), default=0)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
