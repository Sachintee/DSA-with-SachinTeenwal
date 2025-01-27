--- ❤️ ---
# 🚀 _Day 27. Find Duplicate in Array_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/find-duplicate-in-array/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
using namespace std;

class Solution {
public:
    int repeatedNumber(const vector<int>& A) {
        int slow = A[0];
        int fast = A[0];

        // Step 1: Detect a cycle
        do {
            slow = A[slow];
            fast = A[A[fast]];
        } while (slow != fast);

        // Step 2: Find the entry point of the cycle (duplicate)
        slow = A[0];
        while (slow != fast) {
            slow = A[slow];
            fast = A[fast];
        }

        return slow;
    }
};

```

## Code (Java)

```java
import java.util.List;

public class Solution {
    public int repeatedNumber(final List<Integer> A) {
        int slow = A.get(0);
        int fast = A.get(0);

        // Step 1: Detect a cycle
        do {
            slow = A.get(slow);
            fast = A.get(A.get(fast));
        } while (slow != fast);

        // Step 2: Find the entry point of the cycle (duplicate)
        slow = A.get(0);
        while (slow != fast) {
            slow = A.get(slow);
            fast = A.get(fast);
        }

        return slow;
    }
}

```

## Code (Python)

```python
class Solution:
    # @param A : tuple of integers
    # @return an integer
    def repeatedNumber(self, A):
        # Step 1: Detect a cycle
        slow = A[0]
        fast = A[0]
        
        while True:
            slow = A[slow]
            fast = A[A[fast]]
            if slow == fast:
                break
        
        # Step 2: Find the entry point of the cycle
        slow = A[0]
        while slow != fast:
            slow = A[slow]
            fast = A[fast]
        
        return slow

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
 <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>885</h4>
