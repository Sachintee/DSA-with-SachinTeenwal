--- ❤️ ---

# 🚀 _Day 55. Maximum Absolute Difference_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/maximum-absolute-difference/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <algorithm>
#include <climits>

using namespace std;

class Solution {
public:
    int maxArr(vector<int>& A) {
        int n = A.size();
        vector<int> B(n), C(n);
        
        // Compute B[i] = A[i] + i and C[i] = A[i] - i
        for (int i = 0; i < n; i++) {
            B[i] = A[i] + i;
            C[i] = A[i] - i;
        }
        
        // Find the maximum and minimum values in B and C
        int max_B = *max_element(B.begin(), B.end());
        int min_B = *min_element(B.begin(), B.end());
        int max_C = *max_element(C.begin(), C.end());
        int min_C = *min_element(C.begin(), C.end());
        
        // The result is the maximum of (max_B - min_B) and (max_C - min_C)
        return max(max_B - min_B, max_C - min_C);
    }
};
```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public int maxArr(ArrayList<Integer> A) {
        int n = A.size();
        ArrayList<Integer> B = new ArrayList<>();
        ArrayList<Integer> C = new ArrayList<>();
        
        // Compute B[i] = A[i] + i and C[i] = A[i] - i
        for (int i = 0; i < n; i++) {
            B.add(A.get(i) + i);
            C.add(A.get(i) - i);
        }
        
        // Find the maximum and minimum values in B and C
        int max_B = Collections.max(B);
        int min_B = Collections.min(B);
        int max_C = Collections.max(C);
        int min_C = Collections.min(C);
        
        // The result is the maximum of (max_B - min_B) and (max_C - min_C)
        return Math.max(max_B - min_B, max_C - min_C);
    }
}
```

## Code (Python)

```python
class Solution:
    def maxArr(self, A):
        # Compute B[i] = A[i] + i and C[i] = A[i] - i
        B = [A[i] + i for i in range(len(A))]
        C = [A[i] - i for i in range(len(A))]
        
        # Find the maximum and minimum values in B and C
        max_B = max(B)
        min_B = min(B)
        max_C = max(C)
        min_C = min(C)
        
        # The result is the maximum of (max_B - min_B) and (max_C - min_C)
        return max(max_B - min_B, max_C - min_C)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
