
# 🚀 _Day 19. Leaders in an array_ 🧠

Leaders in an array

Arrays
easy

Problem Description

Given an integer array A containing N distinct integers, you have to find all the leaders in the array A.

 An element is leader if it is strictly greater than all the elements to its right side.

NOTE:The rightmost element is always a leader.
The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/leaders-in-an-array)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <vector>
using namespace std;

class Solution {
public:
    // Function to find leaders in the array
    vector<int> solve(vector<int>& A) {
        int n = A.size();
        vector<int> leaders;
        int max_from_right = INT_MIN;

        // Traverse the array from right to left
        for (int i = n - 1; i >= 0; i--) {
            if (A[i] > max_from_right) {
                leaders.push_back(A[i]);
                max_from_right = A[i];
            }
        }

        return leaders;
    }
};
```

## Code (Java)

```java
import java.util.ArrayList;

class Solution {
    // Function to find leaders in the array
    public ArrayList<Integer> solve(int[] A) {
        int n = A.length;
        ArrayList<Integer> leaders = new ArrayList<>();
        int maxFromRight = Integer.MIN_VALUE;

        // Traverse the array from right to left
        for (int i = n - 1; i >= 0; i--) {
            if (A[i] > maxFromRight) {
                leaders.add(A[i]);
                maxFromRight = A[i];
            }
        }

        return leaders;
    }
}
```

## Code (Python)

```python
class Solution:
    # Function to find leaders in the array
    def solve(self, A):
        n = len(A)
        leaders = []
        max_from_right = float('-inf')

        # Traverse the array from right to left
        for i in range(n - 1, -1, -1):
            if A[i] > max_from_right:
                leaders.append(A[i])
                max_from_right = A[i]

        return leaders
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
 <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>485</h4>
