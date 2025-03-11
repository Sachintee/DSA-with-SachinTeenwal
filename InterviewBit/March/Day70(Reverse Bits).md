--- ❤️ ---

# 🚀 _Day 70. Reverse Bits_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/reverse-bits/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
using namespace std;

class Solution {
public:
    unsigned int reverse(unsigned int A) {
        unsigned int result = 0;
        for (int i = 0; i < 32; i++) {
            // Shift result left to make space for the new bit
            result <<= 1;
            // Add the current bit of A to result
            result |= A & 1;
            // Shift A right to process the next bit
            A >>= 1;
        }
        return result;
    }
};

int main() {
    Solution sol;
    unsigned int A = 3; // Example input
    cout << "Reversed bits: " << sol.reverse(A) << endl;
    return 0;
}
```

## Code (Java)

```java
public class Solution {
    public long reverse(long A) {
        long result = 0;
        for (int i = 0; i < 32; i++) {
            // Shift result left to make space for the new bit
            result <<= 1;
            // Add the current bit of A to result
            result |= A & 1;
            // Shift A right to process the next bit
            A >>= 1;
        }
        return result;
    }

    public static void main(String[] args) {
        Solution sol = new Solution();
        long A = 3; // Example input
        System.out.println("Reversed bits: " + sol.reverse(A));
    }
}
```

## Code (Python)

```python
class Solution:
    def reverse(self, A):
        result = 0
        for i in range(32):
            # Shift result left to make space for the new bit
            result <<= 1
            # Add the current bit of A to result
            result |= A & 1
            # Shift A right to process the next bit
            A >>= 1
        return result
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
