
# 🚀 _Day 22. Max Min_ 🧠
\
Problem Description

Given an array A of size N. You need to find the sum of Maximum and Minimum element in the given array.

NOTE: You should make minimum number of comparisons.

The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/max-min-05542f2f-69aa-4253-9cc7-84eb7bf739c4/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <vector>
#include <climits>
using namespace std;

class Solution {
public:
    int solve(vector<int>& A) {
        int minElem = INT_MAX;
        int maxElem = INT_MIN;

        for (int num : A) {
            if (num < minElem) {
                minElem = num;
            }
            if (num > maxElem) {
                maxElem = num;
            }
        }

        return minElem + maxElem;
    }
};

// Example Usage
int main() {
    Solution sol;
    vector<int> A = {-2, 1, -4, 5, 3};
    cout << sol.solve(A) << endl; // Output: 1
    return 0;
}
```

## Code (Java)

```java
import java.util.*;

class Solution {
    public int solve(int[] A) {
        int minElem = Integer.MAX_VALUE;
        int maxElem = Integer.MIN_VALUE;

        for (int num : A) {
            if (num < minElem) {
                minElem = num;
            }
            if (num > maxElem) {
                maxElem = num;
            }
        }

        return minElem + maxElem;
    }

    // Example Usage
    public static void main(String[] args) {
        Solution sol = new Solution();
        int[] A = {-2, 1, -4, 5, 3};
        System.out.println(sol.solve(A)); // Output: 1
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : list of integers
    # @return an integer
    def solve(self, A):
        # Initialize min and max to the first element
        min_elem = float('inf')
        max_elem = float('-inf')

        for num in A:
            if num < min_elem:
                min_elem = num
            if num > max_elem:
                max_elem = num

        return min_elem + max_elem
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
 <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>725</h4>
