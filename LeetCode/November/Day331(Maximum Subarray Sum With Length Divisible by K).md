--- ❤️ ---

# 🚀 _Day . _ 🧠


The problem can be found at the following link: [Problem Link]()

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
    def maxSubarraySum(self, nums: List[int], k: int) -> int:
        f = [inf] * k
        ans = -inf
        s = f[-1] = 0
        for i, x in enumerate(nums):
            s += x
            ans = max(ans, s - f[i % k])
            f[i % k] = min(f[i % k], s)
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
