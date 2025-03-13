--- ❤️ ---

# 🚀 _Day 72. XOR-ing the Subarrays!_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/xor-ing-the-subarrays/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
using namespace std;

class Solution {
public:
    int solve(vector<int>& A) {
        int result = 0;
        int n = A.size();
        for (int i = 0; i < n; i++) {
            // Calculate the frequency of A[i] in all subarrays
            long long freq = (i + 1) * (n - i);
            // If frequency is odd, XOR the element
            if (freq % 2 == 1) {
                result ^= A[i];
            }
        }
        return result;
    }
};
```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public int solve(ArrayList<Integer> A) {
        int result = 0;
        int n = A.size();
        for (int i = 0; i < n; i++) {
            // Calculate the frequency of A[i] in all subarrays
            long freq = (i + 1) * (n - i);
            // If frequency is odd, XOR the element
            if (freq % 2 == 1) {
                result ^= A.get(i);
            }
        }
        return result;
    }
}
```

## Code (Python)

```python
class Solution:
    def solve(self, A):
        result = 0
        n = len(A)
        for i in range(n):
            # Calculate the frequency of A[i] in all subarrays
            freq = (i + 1) * (n - i)
            # If frequency is odd, XOR the element
            if freq % 2 == 1:
                result ^= A[i]
        return result
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
