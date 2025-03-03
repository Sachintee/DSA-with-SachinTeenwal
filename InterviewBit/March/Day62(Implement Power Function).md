--- ❤️ ---

# 🚀 _Day 62. Implement Power Function_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/implement-power-function/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int pow(int x, int n, int d) {
        if (x == 0) return 0;
        if (n == 0) return 1 % d;
        long long result = 1;
        x = x % d;
        while (n > 0) {
            if (n % 2 == 1) {
                result = (result * x) % d;
            }
            x = (x * x) % d;
            n = n / 2;
        }
        return (result + d) % d; // Ensure non-negative result
    }
};
```

## Code (Java)

```java
public class Solution {
    public int pow(int x, int n, int d) {
        if (x == 0) return 0;
        if (n == 0) return 1 % d;
        long result = 1;
        x = x % d;
        while (n > 0) {
            if (n % 2 == 1) {
                result = (result * x) % d;
            }
            x = (x * x) % d;
            n = n / 2;
        }
        return (int) ((result + d) % d); // Ensure non-negative result
    }
}
```

## Code (Python)

```python
class Solution:
    def pow(self, x, n, d):
        if x == 0:
            return 0
        if n == 0:
            return 1 % d
        result = 1
        x = x % d
        while n > 0:
            if n % 2 == 1:
                result = (result * x) % d
            x = (x * x) % d
            n = n // 2
        return result
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
