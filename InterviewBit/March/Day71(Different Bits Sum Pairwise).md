--- ❤️ ---

# 🚀 _Day 71. Different Bits Sum Pairwise_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/different-bits-sum-pairwise/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <algorithm>
using namespace std;

class Solution {
public:
    int cntBits(vector<int>& A) {
        const int MOD = 1e9 + 7;
        int N = A.size();
        long long total = 0;

        // Iterate over each bit position (0 to 31)
        for (int i = 0; i < 32; i++) {
            int count = 0;
            for (int num : A) {
                // Check if the i-th bit is set
                if ((num >> i) & 1) {
                    count++;
                }
            }
            // Calculate the contribution of the i-th bit
            total += (long long)count * (N - count) * 2;
            total %= MOD;
        }

        return (int)total;
    }
};
```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public int cntBits(int[] A) {
        final int MOD = 1000000007;
        int N = A.length;
        long total = 0;

        // Iterate over each bit position (0 to 31)
        for (int i = 0; i < 32; i++) {
            int count = 0;
            for (int num : A) {
                // Check if the i-th bit is set
                if (((num >> i) & 1) == 1) {
                    count++;
                }
            }
            // Calculate the contribution of the i-th bit
            total += (long)count * (N - count) * 2;
            total %= MOD;
        }

        return (int)total;
    }
}
```

## Code (Python)

```python
class Solution:
    def cntBits(self, A):
        MOD = 10**9 + 7
        N = len(A)
        total = 0
        
        # Iterate over each bit position (0 to 31)
        for i in range(32):
            count = 0
            for num in A:
                # Check if the i-th bit is set
                if (num >> i) & 1:
                    count += 1
            # Calculate the contribution of the i-th bit
            total += count * (N - count) * 2
            total %= MOD
        
        return total
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
