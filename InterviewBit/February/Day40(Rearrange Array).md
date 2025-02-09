--- ❤️ ---

# 🚀 _Day 40. Rearrange Array_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/rearrange-array/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
using namespace std;

class Solution {
public:
    void arrange(vector<int> &A) {
        int N = A.size();
        
        // Encoding both old and new values in a single number
        for (int i = 0; i < N; i++) {
            A[i] += (A[A[i]] % N) * N;
        }

        // Extracting new values
        for (int i = 0; i < N; i++) {
            A[i] /= N;
        }
    }
};

```

## Code (Java)

```java
import java.util.*;

class Solution {
    public void arrange(ArrayList<Integer> A) {
        int N = A.size();

        // Encoding both old and new values in a single number
        for (int i = 0; i < N; i++) {
            A.set(i, A.get(i) + (A.get(A.get(i)) % N) * N);
        }

        // Extracting new values
        for (int i = 0; i < N; i++) {
            A.set(i, A.get(i) / N);
        }
    }
}

```

## Code (Python)

```python
class Solution:
    # @param A : list of integers
    # Modify the array A which is passed by reference.
    # You do not need to return anything in this case.
    def arrange(self, A):
        N = len(A)
        
        # Encoding both old and new values in a single number
        for i in range(N):
            A[i] += (A[A[i]] % N) * N
        
        # Extracting new values
        for i in range(N):
            A[i] //= N

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
