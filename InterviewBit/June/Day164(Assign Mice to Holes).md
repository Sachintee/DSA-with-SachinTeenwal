--- ❤️ ---

# 🚀 _Day 164. Assign Mice to Holes_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/assign-mice-to-holes/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <algorithm>
#include <cmath>

using namespace std;

class Solution {
public:
    int mice(vector<int>& A, vector<int>& B) {
        sort(A.begin(), A.end());
        sort(B.begin(), B.end());
        int max_time = 0;
        for (int i = 0; i < A.size(); ++i) {
            max_time = max(max_time, abs(A[i] - B[i]));
        }
        return max_time;
    }
};
```

## Code (Java)

```java
import java.util.Arrays;

class Solution {
    public int mice(int[] A, int[] B) {
        Arrays.sort(A);
        Arrays.sort(B);
        int maxTime = 0;
        for (int i = 0; i < A.length; i++) {
            maxTime = Math.max(maxTime, Math.abs(A[i] - B[i]));
        }
        return maxTime;
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : list of integers
    # @param B : list of integers
    # @return an integer
    def mice(self, A, B):
        A.sort()
        B.sort()
        max_time = 0
        for a, b in zip(A, B):
            max_time = max(max_time, abs(a - b))
        return max_time
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
