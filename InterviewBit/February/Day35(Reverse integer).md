--- ❤️ ---

# 🚀 _Day 35. Reverse integer_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/reverse-integer/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <climits> // For INT_MIN and INT_MAX
using namespace std;

class Solution {
public:
    int reverse(int A) {
        bool isNegative = A < 0;
        A = abs(A);
        
        long long reversedNum = 0; // Use long long to handle overflow
        while (A > 0) {
            int digit = A % 10;
            reversedNum = reversedNum * 10 + digit;
            A = A / 10;
        }
        
        // Add negative sign if the input was negative
        if (isNegative) {
            reversedNum = -reversedNum;
        }
        
        // Check for 32-bit integer overflow
        if (reversedNum < INT_MIN || reversedNum > INT_MAX) {
            return 0;
        }
        
        return static_cast<int>(reversedNum);
    }
};
```

## Code (Java)

```java
class Solution {
    public int reverse(int A) {
        boolean isNegative = A < 0;
        A = Math.abs(A);
        
        long reversedNum = 0; // Use long to handle overflow
        while (A > 0) {
            int digit = A % 10;
            reversedNum = reversedNum * 10 + digit;
            A = A / 10;
        }
        
        // Add negative sign if the input was negative
        if (isNegative) {
            reversedNum = -reversedNum;
        }
        
        // Check for 32-bit integer overflow
        if (reversedNum < Integer.MIN_VALUE || reversedNum > Integer.MAX_VALUE) {
            return 0;
        }
        
        return (int) reversedNum;
    }
}
```

## Code (Python)

```python
class Solution:
    def reverse(self, A):
        # Handle negative numbers
        is_negative = A < 0
        A = abs(A)
        
        reversed_num = 0
        while A > 0:
            digit = A % 10
            reversed_num = reversed_num * 10 + digit
            A = A // 10
        
        # Add negative sign if the input was negative
        if is_negative:
            reversed_num = -reversed_num
        
        # Check for 32-bit integer overflow
        if reversed_num < -2**31 or reversed_num > 2**31 - 1:
            return 0
        
        return reversed_num
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
