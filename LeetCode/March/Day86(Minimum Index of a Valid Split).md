--- ❤️ ---

# 🚀 _Day 86. Minimum Index of a Valid Split_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/minimum-index-of-a-valid-split/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int minimumIndex(vector<int>& nums) {
        int x = 0, cnt = 0;
        unordered_map<int, int> freq;
        for (int v : nums) {
            ++freq[v];
            if (freq[v] > cnt) {
                cnt = freq[v];
                x = v;
            }
        }
        int cur = 0;
        for (int i = 1; i <= nums.size(); ++i) {
            if (nums[i - 1] == x) {
                ++cur;
                if (cur * 2 > i && (cnt - cur) * 2 > nums.size() - i) {
                    return i - 1;
                }
            }
        }
        return -1;
    }
};
```

## Code (Java)

```java
class Solution {
    public int minimumIndex(List<Integer> nums) {
        int x = 0, cnt = 0;
        Map<Integer, Integer> freq = new HashMap<>();
        for (int v : nums) {
            int t = freq.merge(v, 1, Integer::sum);
            if (cnt < t) {
                cnt = t;
                x = v;
            }
        }
        int cur = 0;
        for (int i = 1; i <= nums.size(); ++i) {
            if (nums.get(i - 1) == x) {
                ++cur;
                if (cur * 2 > i && (cnt - cur) * 2 > nums.size() - i) {
                    return i - 1;
                }
            }
        }
        return -1;
    }
}
```

## Code (Python)

```python
class Solution:
    def minimumIndex(self, nums: List[int]) -> int:
        x, cnt = Counter(nums).most_common(1)[0]
        cur = 0
        for i, v in enumerate(nums, 1):
            if v == x:
                cur += 1
                if cur * 2 > i and (cnt - cur) * 2 > len(nums) - i:
                    return i - 1
        return -1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
