--- ❤️ ---

# 🚀 _Day 326. Find Minimum Operations to Make All Elements Divisible by Three_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/find-minimum-operations-to-make-all-elements-divisible-by-three/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp

```

## Code (Java)

```java

```

## Code (Python)

```python
class Solution:
    def minimumOperations(self, nums: List[int]) -> int:
        ans = 0
        for x in nums:
            if mod := x % 3:
                ans += min(mod, 3 - mod)
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
