--- ❤️ ---

# 🚀 _Day 333. Minimum Operations to Make Array Sum Divisible by K_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/minimum-operations-to-make-array-sum-divisible-by-k/?)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int minOperations(vector<int>& nums, int k) {
        return reduce(nums.begin(), nums.end(), 0) % k;
    }
};
```

## Code (Java)

```java

```

## Code (Python)

```python
class Solution:
    def minOperations(self, nums: List[int], k: int) -> int:
        return sum(nums) % k
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
