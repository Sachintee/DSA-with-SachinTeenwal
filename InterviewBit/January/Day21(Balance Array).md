
# 🚀 _Day 21. Balance Array_ 🧠

Problem Description

Given an integer array A of size N. You need to count the number of special elements in the given array.

A element is special if removal of that element make the array balanced.

Array will be balanced if sum of even index element equal to sum of odd index element.

The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/balance-array/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
using namespace std;

class Solution {
public:
    int solve(vector<int> &A) {
        int n = A.size();
        if (n == 1) return 1;

        vector<int> oddPrefix(n, 0), evenPrefix(n, 0);

        // Compute prefix sums
        for (int i = 0; i < n; i++) {
            oddPrefix[i] = (i > 0 ? oddPrefix[i - 1] : 0);
            evenPrefix[i] = (i > 0 ? evenPrefix[i - 1] : 0);

            if (i % 2 == 0) {
                evenPrefix[i] += A[i];
            } else {
                oddPrefix[i] += A[i];
            }
        }

        // Count special elements
        int count = 0;
        for (int i = 0; i < n; i++) {
            int evenSum = (i > 0 ? evenPrefix[i - 1] : 0);
            int oddSum = (i > 0 ? oddPrefix[i - 1] : 0);

            if (i < n - 1) {
                evenSum += oddPrefix[n - 1] - oddPrefix[i];
                oddSum += evenPrefix[n - 1] - evenPrefix[i];
            }

            if (evenSum == oddSum) count++;
        }

        return count;
    }
};
```

## Code (Java)

```java
import java.util.*;

class Solution {
    public int solve(int[] A) {
        int n = A.length;
        if (n == 1) return 1;

        int[] oddPrefix = new int[n];
        int[] evenPrefix = new int[n];

        // Compute prefix sums
        for (int i = 0; i < n; i++) {
            oddPrefix[i] = (i > 0 ? oddPrefix[i - 1] : 0);
            evenPrefix[i] = (i > 0 ? evenPrefix[i - 1] : 0);

            if (i % 2 == 0) {
                evenPrefix[i] += A[i];
            } else {
                oddPrefix[i] += A[i];
            }
        }

        // Count special elements
        int count = 0;
        for (int i = 0; i < n; i++) {
            int evenSum = (i > 0 ? evenPrefix[i - 1] : 0);
            int oddSum = (i > 0 ? oddPrefix[i - 1] : 0);

            if (i < n - 1) {
                evenSum += oddPrefix[n - 1] - oddPrefix[i];
                oddSum += evenPrefix[n - 1] - evenPrefix[i];
            }

            if (evenSum == oddSum) count++;
        }

        return count;
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : list of integers
    # @return an integer
    def solve(self, A):
        n = len(A)
        if n == 1:
            return 1

        # Prefix sums for odd and even indices
        odd_prefix = [0] * n
        even_prefix = [0] * n

        # Compute prefix sums
        for i in range(n):
            odd_prefix[i] = odd_prefix[i - 1] if i > 0 else 0
            even_prefix[i] = even_prefix[i - 1] if i > 0 else 0

            if i % 2 == 0:
                even_prefix[i] += A[i]
            else:
                odd_prefix[i] += A[i]

        # Count special elements
        count = 0
        for i in range(n):
            even_sum = even_prefix[i - 1] if i > 0 else 0
            odd_sum = odd_prefix[i - 1] if i > 0 else 0

            if i < n - 1:
                even_sum += odd_prefix[n - 1] - odd_prefix[i]
                odd_sum += even_prefix[n - 1] - even_prefix[i]

            if even_sum == odd_sum:
                count += 1

        return count
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
 <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>658</h4>
