--- ❤️ ---

# 🚀 _Day 303. Minimum Number of Increments on Subarrays to Form a Target Array_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/minimum-number-of-increments-on-subarrays-to-form-a-target-array/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int minNumberOperations(vector<int>& target) {
        int f = target[0];
        for (int i = 1; i < target.size(); ++i) {
            if (target[i] > target[i - 1]) {
                f += target[i] - target[i - 1];
            }
        }
        return f;
    }
};
```

## Code (Java)

```java
class Solution {
    public int minNumberOperations(int[] target) {
        int f = target[0];
        for (int i = 1; i < target.length; ++i) {
            if (target[i] > target[i - 1]) {
                f += target[i] - target[i - 1];
            }
        }
        return f;
    }
}
```

## Code (Python)

```python
class Solution:
    def minNumberOperations(self, target: List[int]) -> int:
        return target[0] + sum(max(0, b - a) for a, b in pairwise(target))
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
