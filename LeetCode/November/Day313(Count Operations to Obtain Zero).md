--- ❤️ ---

# 🚀 _Day 313. Count Operations to Obtain Zero_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/count-operations-to-obtain-zero/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int countOperations(int num1, int num2) {
        int ans = 0;
        for (; num1 && num2; ++ans) {
            if (num1 >= num2) {
                num1 -= num2;
            } else {
                num2 -= num1;
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int countOperations(int num1, int num2) {
        int ans = 0;
        for (; num1 != 0 && num2 != 0; ++ans) {
            if (num1 >= num2) {
                num1 -= num2;
            } else {
                num2 -= num1;
            }
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def countOperations(self, num1: int, num2: int) -> int:
        ans = 0
        while num1 and num2:
            if num1 >= num2:
                num1 -= num2
            else:
                num2 -= num1
            ans += 1
        return ans
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
