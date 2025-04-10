--- ❤️ ---

# 🚀 _Day 100. Array 3 Pointers_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/array-3-pointers/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <algorithm>
#include <climits>
#include <cmath>

using namespace std;

class Solution {
public:
    int minimize(const vector<int> &A, const vector<int> &B, const vector<int> &C) {
        int i = 0, j = 0, k = 0;
        int min_max_diff = INT_MAX;
        
        int len_a = A.size(), len_b = B.size(), len_c = C.size();
        
        while (i < len_a && j < len_b && k < len_c) {
            int current_a = A[i];
            int current_b = B[j];
            int current_c = C[k];
            
            int current_max_diff = max({abs(current_a - current_b), abs(current_b - current_c), abs(current_c - current_a)});
            if (current_max_diff < min_max_diff) {
                min_max_diff = current_max_diff;
            }
            
            // Move the pointer which points to the smallest value among the three
            if (current_a <= current_b && current_a <= current_c) {
                i++;
            } else if (current_b <= current_a && current_b <= current_c) {
                j++;
            } else {
                k++;
            }
        }
        
        return min_max_diff;
    }
};
```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public int minimize(final List<Integer> A, final List<Integer> B, final List<Integer> C) {
        int i = 0, j = 0, k = 0;
        int minMaxDiff = Integer.MAX_VALUE;
        
        int lenA = A.size(), lenB = B.size(), lenC = C.size();
        
        while (i < lenA && j < lenB && k < lenC) {
            int currentA = A.get(i);
            int currentB = B.get(j);
            int currentC = C.get(k);
            
            int currentMaxDiff = Math.max(Math.abs(currentA - currentB), 
                                         Math.max(Math.abs(currentB - currentC), 
                                                 Math.abs(currentC - currentA)));
            if (currentMaxDiff < minMaxDiff) {
                minMaxDiff = currentMaxDiff;
            }
            
            // Move the pointer which points to the smallest value among the three
            if (currentA <= currentB && currentA <= currentC) {
                i++;
            } else if (currentB <= currentA && currentB <= currentC) {
                j++;
            } else {
                k++;
            }
        }
        
        return minMaxDiff;
    }
}
```

## Code (Python)

```python
class Solution:
    def minimize(self, A, B, C):
        i, j, k = 0, 0, 0
        min_max_diff = float('inf')
        
        len_a, len_b, len_c = len(A), len(B), len(C)
        
        while i < len_a and j < len_b and k < len_c:
            current_a = A[i]
            current_b = B[j]
            current_c = C[k]
            
            current_max_diff = max(abs(current_a - current_b), abs(current_b - current_c), abs(current_c - current_a))
            if current_max_diff < min_max_diff:
                min_max_diff = current_max_diff
            
            # Move the pointer which points to the smallest value among the three
            if current_a <= current_b and current_a <= current_c:
                i += 1
            elif current_b <= current_a and current_b <= current_c:
                j += 1
            else:
                k += 1
        
        return min_max_diff
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
