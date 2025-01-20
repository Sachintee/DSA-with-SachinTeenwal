# 🚀 _Day 20. Sort array with squares_ 🧠
Sort array with squares!

Arrays
easy

Problem Description

Given a sorted array A containing N integers both positive and negative.

You need to create another array containing the squares of all the elements in A and return it in non-decreasing order.

Try to this in O(N) time.

The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/sort-array-with-squares/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <vector>
#include <cmath>
using namespace std;

class Solution {
public:
    vector<int> solve(vector<int>& A) {
        int n = A.size();
        vector<int> result(n);
        int left = 0, right = n - 1, index = n - 1;

        while (left <= right) {
            if (abs(A[left]) > abs(A[right])) {
                result[index--] = A[left] * A[left];
                left++;
            } else {
                result[index--] = A[right] * A[right];
                right--;
            }
        }

        return result;
    }
};

// Example usage
int main() {
    Solution sol;
    vector<int> A = {-6, -3, -1, 2, 4, 5};
    vector<int> result = sol.solve(A);

    for (int num : result) {
        cout << num << " ";
    }
    cout << endl; // Output: 1 4 9 16 25 36

    return 0;
}
```

## Code (Java)

```java
import java.util.ArrayList;
import java.util.Collections;

class Solution {
    public ArrayList<Integer> solve(ArrayList<Integer> A) {
        int n = A.size();
        ArrayList<Integer> result = new ArrayList<>(Collections.nCopies(n, 0));
        int left = 0, right = n - 1, index = n - 1;

        while (left <= right) {
            if (Math.abs(A.get(left)) > Math.abs(A.get(right))) {
                result.set(index--, A.get(left) * A.get(left));
                left++;
            } else {
                result.set(index--, A.get(right) * A.get(right));
                right--;
            }
        }

        return result;
    }

    public static void main(String[] args) {
        Solution sol = new Solution();
        ArrayList<Integer> A = new ArrayList<>();
        Collections.addAll(A, -6, -3, -1, 2, 4, 5);
        ArrayList<Integer> result = sol.solve(A);

        System.out.println(result); // Output: [1, 4, 9, 16, 25, 36]
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : list of integers
    # @return a list of integers
    def solve(self, A):
        n = len(A)
        result = [0] * n
        left, right = 0, n - 1
        index = n - 1

        while left <= right:
            if abs(A[left]) > abs(A[right]):
                result[index] = A[left] ** 2
                left += 1
            else:
                result[index] = A[right] ** 2
                right -= 1
            index -= 1

        return result
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
 <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>852</h4>
