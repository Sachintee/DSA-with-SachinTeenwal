--- ❤️ ---

# 🚀 _Day 298. Calculate Money in Leetcode Bank_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/calculate-money-in-leetcode-bank/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int totalMoney(int n) {
        int k = n / 7, b = n % 7;
        int s1 = (28 + 28 + 7 * (k - 1)) * k / 2;
        int s2 = (k + 1 + k + 1 + b - 1) * b / 2;
        return s1 + s2;
    }
};
```

## Code (Java)

```java
class Solution {
    public int totalMoney(int n) {
        int k = n / 7, b = n % 7;
        int s1 = (28 + 28 + 7 * (k - 1)) * k / 2;
        int s2 = (k + 1 + k + 1 + b - 1) * b / 2;
        return s1 + s2;
    }
}
```

## Code (Python)

```python
class Solution:
    def totalMoney(self, n: int) -> int:
        k, b = divmod(n, 7)
        s1 = (28 + 28 + 7 * (k - 1)) * k // 2
        s2 = (k + 1 + k + 1 + b - 1) * b // 2
        return s1 + s2
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
