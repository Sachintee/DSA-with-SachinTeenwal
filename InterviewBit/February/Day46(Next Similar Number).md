--- ❤️ ---

# 🚀 _Day 46. Next Similar Number_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/next-similar-number/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <bits/stdc++.h>
using namespace std;

class Solution {
public:
    string solve(string A) {
        int n = A.size();
        int pivot = -1;

        // Step 1: Find the pivot
        for (int i = n - 2; i >= 0; i--) {
            if (A[i] < A[i + 1]) {
                pivot = i;
                break;
            }
        }

        if (pivot == -1) return "-1";

        // Step 2: Find the smallest greater element than A[pivot]
        for (int i = n - 1; i > pivot; i--) {
            if (A[i] > A[pivot]) {
                swap(A[i], A[pivot]);
                break;
            }
        }

        // Step 3: Sort the suffix after pivot
        reverse(A.begin() + pivot + 1, A.end());

        return A;
    }
};

```

## Code (Java)

```java
import java.util.*;

class Solution {
    public String solve(String A) {
        char[] arr = A.toCharArray();
        int n = arr.length;
        int pivot = -1;

        // Step 1: Find the pivot
        for (int i = n - 2; i >= 0; i--) {
            if (arr[i] < arr[i + 1]) {
                pivot = i;
                break;
            }
        }

        if (pivot == -1) return "-1";

        // Step 2: Find the smallest greater element than arr[pivot]
        for (int i = n - 1; i > pivot; i--) {
            if (arr[i] > arr[pivot]) {
                char temp = arr[i];
                arr[i] = arr[pivot];
                arr[pivot] = temp;
                break;
            }
        }

        // Step 3: Sort the suffix after pivot
        Arrays.sort(arr, pivot + 1, n);

        return new String(arr);
    }
}

```

## Code (Python)

```python
class Solution:
    def solve(self, A):
        A = list(A)
        n = len(A)
        pivot = -1

        # Step 1: Find the pivot
        for i in range(n - 2, -1, -1):
            if A[i] < A[i + 1]:
                pivot = i
                break

        if pivot == -1:
            return "-1"

        # Step 2: Find the smallest greater element than A[pivot]
        for i in range(n - 1, pivot, -1):
            if A[i] > A[pivot]:
                A[i], A[pivot] = A[pivot], A[i]
                break

        # Step 3: Sort the suffix after pivot
        A[pivot + 1:] = sorted(A[pivot + 1:])

        return ''.join(A)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
