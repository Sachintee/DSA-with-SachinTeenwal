--- ❤️ ---

# 🚀 _Day 87. Counting Triangles_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/counting-triangles/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <algorithm>
using namespace std;

class Solution {
public:
    int nTriang(vector<int>& A) {
        const int MOD = 1e9 + 7;
        sort(A.begin(), A.end());
        int n = A.size();
        int count = 0;
        
        for (int i = 0; i < n - 2; ++i) {
            int k = i + 2;
            for (int j = i + 1; j < n - 1; ++j) {
                while (k < n && A[i] + A[j] > A[k]) {
                    ++k;
                }
                if (k > j) {
                    count = (count + (k - j - 1)) % MOD;
                }
            }
        }
        return count;
    }
};
```

## Code (Java)

```java
import java.util.Arrays;

class Solution {
    public int nTriang(int[] A) {
        final int MOD = 1000000007;
        Arrays.sort(A);
        int n = A.length;
        int count = 0;
        
        for (int i = 0; i < n - 2; ++i) {
            int k = i + 2;
            for (int j = i + 1; j < n - 1; ++j) {
                while (k < n && A[i] + A[j] > A[k]) {
                    ++k;
                }
                if (k > j) {
                    count = (count + (k - j - 1)) % MOD;
                }
            }
        }
        return count;
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : list of integers
    # @return an integer
    def nTriang(self, A):
        MOD = 10**9 + 7
        A.sort()
        n = len(A)
        count = 0
        
        for i in range(n - 2):
            k = i + 2
            for j in range(i + 1, n - 1):
                while k < n and A[i] + A[j] > A[k]:
                    k += 1
                if k > j:
                    count += k - j - 1
        return count % MOD
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
