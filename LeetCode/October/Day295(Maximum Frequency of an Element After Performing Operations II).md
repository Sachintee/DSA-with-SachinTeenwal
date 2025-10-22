--- ❤️ ---

# 🚀 _Day 295. Maximum Frequency of an Element After Performing Operations II_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/maximum-frequency-of-an-element-after-performing-operations-ii/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int maxFrequency(vector<int>& nums, int k, int numOperations) {
        unordered_map<int, int> cnt;
        map<int, int> d;

        for (int x : nums) {
            cnt[x]++;
            d[x];
            d[x - k]++;
            d[x + k + 1]--;
        }

        int ans = 0, s = 0;
        for (const auto& [x, t] : d) {
            s += t;
            ans = max(ans, min(s, cnt[x] + numOperations));
        }

        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int maxFrequency(int[] nums, int k, int numOperations) {
        Map<Integer, Integer> cnt = new HashMap<>();
        TreeMap<Integer, Integer> d = new TreeMap<>();
        for (int x : nums) {
            cnt.merge(x, 1, Integer::sum);
            d.putIfAbsent(x, 0);
            d.merge(x - k, 1, Integer::sum);
            d.merge(x + k + 1, -1, Integer::sum);
        }
        int ans = 0, s = 0;
        for (var e : d.entrySet()) {
            int x = e.getKey(), t = e.getValue();
            s += t;
            ans = Math.max(ans, Math.min(s, cnt.getOrDefault(x, 0) + numOperations));
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def maxFrequency(self, nums: List[int], k: int, numOperations: int) -> int:
        cnt = defaultdict(int)
        d = defaultdict(int)
        for x in nums:
            cnt[x] += 1
            d[x] += 0
            d[x - k] += 1
            d[x + k + 1] -= 1
        ans = s = 0
        for x, t in sorted(d.items()):
            s += t
            ans = max(ans, min(s, cnt[x] + numOperations))
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
