--- ❤️ ---

# 🚀 _Day 69. Number of 1 Bits_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/number-of-1-bits/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
using namespace std;

class Solution {
public:
    int numSetBits(unsigned int A) {
        int count = 0;
        while (A > 0) {
            // Check if the LSB is 1
            if (A & 1) {
                count++;
            }
            // Right-shift A by 1 bit
            A >>= 1;
        }
        return count;
    }
};

int main() {
    Solution sol;
    unsigned int A = 11; // Example input
    cout << "Number of 1 bits: " << sol.numSetBits(A) << endl;
    return 0;
}
```

## Code (Java)

```java
public class Solution {
    public int numSetBits(long A) {
        int count = 0;
        while (A > 0) {
            // Check if the LSB is 1
            if ((A & 1) == 1) {
                count++;
            }
            // Right-shift A by 1 bit
            A >>= 1;
        }
        return count;
    }

    public static void main(String[] args) {
        Solution sol = new Solution();
        long A = 11; // Example input
        System.out.println("Number of 1 bits: " + sol.numSetBits(A));
    }
}
```

## Code (Python)

```python
class Solution:
    def numSetBits(self, A):
        count = 0
        while A > 0:
            # Check if the LSB is 1
            if A & 1:
                count += 1
            # Right-shift A by 1 bit
            A >>= 1
        return count
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
