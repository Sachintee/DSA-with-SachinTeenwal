--- ❤️ ---

# 🚀 _Day 42. Power Of Two Integers_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/power-of-two-integers/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <cmath>
#include <iostream>

class Solution {
public:
    int isPower(int A) {
        if (A == 1) {
            return 1;
        }
        
        for (int p = 2; p <= log2(A); p++) {
            int a = round(pow(A, 1.0 / p));
            if (pow(a, p) == A) {
                return 1;
            }
        }
        
        return 0;
    }
};

// Example usage
int main() {
    Solution sol;
    std::cout << sol.isPower(4) << std::endl;  // Output: 1
    std::cout << sol.isPower(8) << std::endl;  // Output: 1
    std::cout << sol.isPower(10) << std::endl; // Output: 0
    return 0;
}
```

## Code (Java)

```java
public class Solution {
    public int isPower(int A) {
        if (A == 1) {
            return 1;
        }
        
        for (int p = 2; p <= Math.log(A) / Math.log(2); p++) {
            int a = (int) Math.round(Math.pow(A, 1.0 / p));
            if (Math.pow(a, p) == A) {
                return 1;
            }
        }
        
        return 0;
    }

    // Example usage
    public static void main(String[] args) {
        Solution sol = new Solution();
        System.out.println(sol.isPower(4));  // Output: 1
        System.out.println(sol.isPower(8));  // Output: 1
        System.out.println(sol.isPower(10)); // Output: 0
    }
}
```

## Code (Python)

```python
import math

class Solution:
    def isPower(self, A):
        if A == 1:
            return 1
        
        for p in range(2, int(math.log(A, 2)) + 1):
            a = round(A ** (1 / p))
            if a ** p == A:
                return 1
        
        return 0
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
