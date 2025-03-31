--- ❤️ ---

# 🚀 _Day 90. Pair With Given Difference_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/pair-with-given-difference/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <algorithm>

using namespace std;

class Solution {
public:
    int solve(vector<int>& A, int B) {
        sort(A.begin(), A.end());
        int n = A.size();
        int i = 0, j = 1;
        while (i < n && j < n) {
            if (i != j && A[j] - A[i] == B) {
                return 1;
            } else if (A[j] - A[i] < B) {
                j++;
            } else {
                i++;
            }
        }
        return 0;
    }
};
```

## Code (Java)

```java
import java.util.Arrays;

public class Solution {
    public int solve(int[] A, int B) {
        Arrays.sort(A);
        int n = A.length;
        int i = 0, j = 1;
        while (i < n && j < n) {
            if (i != j && A[j] - A[i] == B) {
                return 1;
            } else if (A[j] - A[i] < B) {
                j++;
            } else {
                i++;
            }
        }
        return 0;
    }
}
```

## Code (Python)

```python
class Solution:
    def solve(self, A, B):
        A.sort()
        n = len(A)
        i, j = 0, 1
        while i < n and j < n:
            if i != j and A[j] - A[i] == B:
                return 1
            elif A[j] - A[i] < B:
                j += 1
            else:
                i += 1
        return 0
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
