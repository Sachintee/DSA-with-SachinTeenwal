--- ❤️ ---

# 🚀 _Day 58. Max Distance_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/max-distance/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <algorithm>

using namespace std;

class Solution {
public:
    int maximumGap(vector<int> &A) {
        if (A.empty()) return 0;
        
        int n = A.size();
        vector<int> left_min(n), right_max(n);

        // Fill left_min array
        left_min[0] = A[0];
        for (int i = 1; i < n; i++) {
            left_min[i] = min(left_min[i - 1], A[i]);
        }

        // Fill right_max array
        right_max[n - 1] = A[n - 1];
        for (int i = n - 2; i >= 0; i--) {
            right_max[i] = max(right_max[i + 1], A[i]);
        }

        // Use two pointers to find the maximum gap
        int i = 0, j = 0, max_gap = 0;
        while (i < n && j < n) {
            if (left_min[i] <= right_max[j]) {
                max_gap = max(max_gap, j - i);
                j++;
            } else {
                i++;
            }
        }

        return max_gap;
    }
};

```

## Code (Java)

```java
import java.util.*;

class Solution {
    public int maximumGap(int[] A) {
        if (A == null || A.length == 0) return 0;

        int n = A.length;
        int[] leftMin = new int[n];
        int[] rightMax = new int[n];

        // Fill leftMin array
        leftMin[0] = A[0];
        for (int i = 1; i < n; i++) {
            leftMin[i] = Math.min(leftMin[i - 1], A[i]);
        }

        // Fill rightMax array
        rightMax[n - 1] = A[n - 1];
        for (int i = n - 2; i >= 0; i--) {
            rightMax[i] = Math.max(rightMax[i + 1], A[i]);
        }

        // Use two pointers to find the maximum gap
        int i = 0, j = 0, maxGap = 0;
        while (i < n && j < n) {
            if (leftMin[i] <= rightMax[j]) {
                maxGap = Math.max(maxGap, j - i);
                j++;
            } else {
                i++;
            }
        }

        return maxGap;
    }
}

```

## Code (Python)

```python
class Solution:
    def maximumGap(self, A):
        if not A:
            return 0
        
        n = len(A)
        # Create arrays to store the minimum from the left and maximum from the right
        left_min = [0] * n
        right_max = [0] * n
        
        # Fill left_min array
        left_min[0] = A[0]
        for i in range(1, n):
            left_min[i] = min(left_min[i - 1], A[i])
        
        # Fill right_max array
        right_max[-1] = A[-1]
        for i in range(n - 2, -1, -1):
            right_max[i] = max(right_max[i + 1], A[i])
        
        # Use two pointers to find the maximum gap
        i = j = 0
        max_gap = 0
        while i < n and j < n:
            if left_min[i] <= right_max[j]:
                max_gap = max(max_gap, j - i)
                j += 1
            else:
                i += 1
        
        return max_gap
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
