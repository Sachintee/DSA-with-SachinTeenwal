--- ❤️ ---

# 🚀 _Day 38. Grid Unique Paths_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/grid-unique-paths/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <bits/stdc++.h>
using namespace std;

class Solution {
public:
    int uniquePaths(int A, int B) {
        int n = A + B - 2;  // Total moves
        int r = A - 1;  // Downward moves
        long long res = 1;  
        
        // Compute C(n, r) iteratively to avoid factorial overflow
        for (int i = 0; i < r; i++) {
            res = res * (n - i) / (i + 1);
        }
        return (int)res;
    }
};

// Driver Code
int main() {
    Solution sol;
    int A = 2, B = 2;
    cout << sol.uniquePaths(A, B) << endl;  // Output: 2
    return 0;
}

```

## Code (Java)

```java
class Solution {
    public int uniquePaths(int A, int B) {
        int n = A + B - 2;  // Total moves
        int r = A - 1;  // Downward moves
        long res = 1;

        // Compute C(n, r) iteratively
        for (int i = 0; i < r; i++) {
            res = res * (n - i) / (i + 1);
        }
        return (int) res;
    }

    // Driver Code
    public static void main(String[] args) {
        Solution sol = new Solution();
        int A = 2, B = 2;
        System.out.println(sol.uniquePaths(A, B));  // Output: 2
    }
}

```

## Code (Python)

```python
import math

class Solution:
    # @param A : integer
    # @param B : integer
    # @return an integer
    def uniquePaths(self, A, B):
        return math.comb(A + B - 2, A - 1)  # Equivalent to (A+B-2)! / ((A-1)! * (B-1)!)

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
