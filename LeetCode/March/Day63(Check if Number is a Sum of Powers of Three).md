--- ❤️ ---

# 🚀 _Day 63. Check if Number is a Sum of Powers of Three_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/check-if-number-is-a-sum-of-powers-of-three/submissions/1562637205/?envType=daily-question&envId=2025-03-04)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    bool checkPowersOfThree(int n) {
        while (n) {
            if (n % 3 > 1) return false;
            n /= 3;
        }
        return true;
    }
};
```

## Code (Java)

```java
class Solution {
    public boolean checkPowersOfThree(int n) {
        while (n > 0) {
            if (n % 3 > 1) {
                return false;
            }
            n /= 3;
        }
        return true;
    }
}
```

## Code (Python)

```python
class Solution:
    def checkPowersOfThree(self, n: int) -> bool:
        while n:
            if n % 3 > 1:
                return False
            n //= 3
        return True
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
