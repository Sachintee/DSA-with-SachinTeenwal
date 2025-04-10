--- ❤️ ---

# 🚀 _Day 99. Minimum Operations to Make Array Values Equal to K_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/minimum-operations-to-make-array-values-equal-to-k/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int minOperations(vector<int>& nums, int k) {
        unordered_set<int> s;
        int mi = INT_MAX;
        for (int x : nums) {
            if (x < k) {
                return -1;
            }
            mi = min(mi, x);
            s.insert(x);
        }
        return s.size() - (mi == k);
    }
};
```

## Code (Java)

```java
class Solution {
    public int minOperations(int[] nums, int k) {
        Set<Integer> s = new HashSet<>();
        int mi = 1 << 30;
        for (int x : nums) {
            if (x < k) {
                return -1;
            }
            mi = Math.min(mi, x);
            s.add(x);
        }
        return s.size() - (mi == k ? 1 : 0);
    }
}
```

## Code (Python)

```python
class Solution:
    def minOperations(self, nums: List[int], k: int) -> int:
        s = set()
        mi = inf
        for x in nums:
            if x < k:
                return -1
            mi = min(mi, x)
            s.add(x)
        return len(s) - int(k == mi)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
