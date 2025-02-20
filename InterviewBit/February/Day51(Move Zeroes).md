--- ❤️ ---

# 🚀 _Day 51. Move Zeroes_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/move-zeroes/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
using namespace std;

class Solution {
public:
    vector<int> solve(vector<int>& A) {
        int writePointer = 0;

        // Move all non-zero elements to the front
        for (int readPointer = 0; readPointer < A.size(); readPointer++) {
            if (A[readPointer] != 0) {
                A[writePointer] = A[readPointer];
                writePointer++;
            }
        }

        // Fill the remaining positions with zeros
        for (int i = writePointer; i < A.size(); i++) {
            A[i] = 0;
        }

        return A;
    }
};
```

## Code (Java)

```java
import java.util.Arrays;

class Solution {
    public int[] solve(int[] A) {
        int writePointer = 0;

        // Move all non-zero elements to the front
        for (int readPointer = 0; readPointer < A.length; readPointer++) {
            if (A[readPointer] != 0) {
                A[writePointer] = A[readPointer];
                writePointer++;
            }
        }

        // Fill the remaining positions with zeros
        for (int i = writePointer; i < A.length; i++) {
            A[i] = 0;
        }

        return A;
    }
}
```

## Code (Python)

```python
class Solution:
    def solve(self, A):
        # Initialize a pointer for the position to place the next non-zero element
        write_pointer = 0
        
        # Move all non-zero elements to the front
        for read_pointer in range(len(A)):
            if A[read_pointer] != 0:
                A[write_pointer] = A[read_pointer]
                write_pointer += 1
        
        # Fill the remaining positions with zeros
        for i in range(write_pointer, len(A)):
            A[i] = 0
        
        return A
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
