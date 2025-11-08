--- ❤️ ---

# 🚀 _Day 312. Minimum One Bit Operations to Make Integers Zero_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/minimum-one-bit-operations-to-make-integers-zero/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int minimumOneBitOperations(int n) {
        int ans = 0;
        for (; n > 0; n >>= 1) {
            ans ^= n;
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int minimumOneBitOperations(int n) {
        int ans = 0;
        for (; n > 0; n >>= 1) {
            ans ^= n;
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def minimumOneBitOperations(self, n: int) -> int:
        ans = 0
        while n:
            ans ^= n
            n >>= 1
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
