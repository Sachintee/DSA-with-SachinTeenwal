--- ❤️ ---

# 🚀 _Day 41. Greatest Common Divisor_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/greatest-common-divisor/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int gcd(int A, int B) {
        while (B != 0) {
            int temp = B;
            B = A % B;
            A = temp;
        }
        return A;
    }
};
```

## Code (Java)

```java
public class Solution {
    public int gcd(int A, int B) {
        while (B != 0) {
            int temp = B;
            B = A % B;
            A = temp;
        }
        return A;
    }
}
```

## Code (Python)

```python
class Solution:
    def gcd(self, A, B):
        while B:
            A, B = B, A % B
        return A
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
