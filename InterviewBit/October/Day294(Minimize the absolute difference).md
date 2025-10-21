--- ❤️ ---

# 🚀 _Day 294. Minimize the absolute difference_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/minimize-the-absolute-difference/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <bits/stdc++.h>
using namespace std;

class Solution {
public:
    int solve(vector<int> &A, vector<int> &B, vector<int> &C) {
        int i = A.size() - 1;
        int j = B.size() - 1;
        int k = C.size() - 1;
        int minDiff = INT_MAX;

        while (i >= 0 && j >= 0 && k >= 0) {
            int a = A[i], b = B[j], c = C[k];
            int maxVal = max({a, b, c});
            int minVal = min({a, b, c});
            minDiff = min(minDiff, maxVal - minVal);

            // Move the pointer of the max element
            if (maxVal == a) i--;
            else if (maxVal == b) j--;
            else k--;
        }

        return minDiff;
    }
};

// Example usage
// int main() {
//     vector<int> A = {1, 4, 5, 8, 10};
//     vector<int> B = {6, 9, 15};
//     vector<int> C = {2, 3, 6, 6};
//     Solution obj;
//     cout << obj.solve(A, B, C);
//     return 0;
// }

```

## Code (Java)

```java
public class Solution {
    public int solve(ArrayList<Integer> A, ArrayList<Integer> B, ArrayList<Integer> C) {
        int i = A.size() - 1;
        int j = B.size() - 1;
        int k = C.size() - 1;
        int minDiff = Integer.MAX_VALUE;

        while (i >= 0 && j >= 0 && k >= 0) {
            int a = A.get(i);
            int b = B.get(j);
            int c = C.get(k);

            int maxVal = Math.max(a, Math.max(b, c));
            int minVal = Math.min(a, Math.min(b, c));
            int diff = maxVal - minVal;

            // Update minimum difference
            if (diff < minDiff)
                minDiff = diff;

            // Move the pointer with the maximum value backward
            if (maxVal == a)
                i--;
            else if (maxVal == b)
                j--;
            else
                k--;
        }

        return minDiff;
    }
}

```

## Code (Python)

```python
class Solution:
    def solve(self, A, B, C):
        i = len(A) - 1
        j = len(B) - 1
        k = len(C) - 1
        min_diff = float('inf')

        while i >= 0 and j >= 0 and k >= 0:
            a, b, c = A[i], B[j], C[k]
            max_val = max(a, b, c)
            min_val = min(a, b, c)
            diff = max_val - min_val
            min_diff = min(min_diff, diff)

            if max_val == a:
                i -= 1
            elif max_val == b:
                j -= 1
            else:
                k -= 1

        return min_diff


# Example:
# A = [1, 4, 5, 8, 10]
# B = [6, 9, 15]
# C = [2, 3, 6, 6]
# print(Solution().solve(A, B, C))  # Output: 1

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
