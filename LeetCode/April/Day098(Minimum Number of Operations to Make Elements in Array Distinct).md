--- ❤️ ---

# 🚀 _Day 98. Minimum Number of Operations to Make Elements in Array Distinct_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/minimum-number-of-operations-to-make-elements-in-array-distinct/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int minimumOperations(vector<int>& nums) {
        unordered_set<int> s;
        for (int i = nums.size() - 1; ~i; --i) {
            if (s.contains(nums[i])) {
                return i / 3 + 1;
            }
            s.insert(nums[i]);
        }
        return 0;
    }
};
```

## Code (Java)

```java
class Solution {
    public int minimumOperations(int[] nums) {
        Set<Integer> s = new HashSet<>();
        for (int i = nums.length - 1; i >= 0; --i) {
            if (!s.add(nums[i])) {
                return i / 3 + 1;
            }
        }
        return 0;
    }
}
```

## Code (Python)

```python
class Solution:
    def minimumOperations(self, nums: List[int]) -> int:
        s = set()
        for i in range(len(nums) - 1, -1, -1):
            if nums[i] in s:
                return i // 3 + 1
            s.add(nums[i])
        return 0
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
