--- ❤️ ---

# 🚀 _Day 61. Smaller or equal elements
_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/smaller-or-equal-elements/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
using namespace std;

class Solution {
public:
    int solve(vector<int>& A, int B) {
        int left = 0, right = A.size() - 1;
        int count = 0;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (A[mid] <= B) {
                count = mid + 1;
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        return count;
    }
};
```

## Code (Java)

```java
import java.util.ArrayList;

public class Solution {
    public int solve(ArrayList<Integer> A, int B) {
        int left = 0, right = A.size() - 1;
        int count = 0;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (A.get(mid) <= B) {
                count = mid + 1;
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        return count;
    }
}
```

## Code (Python)

```python
class Solution:
    def solve(self, A, B):
        left, right = 0, len(A) - 1
        count = 0
        while left <= right:
            mid = (left + right) // 2
            if A[mid] <= B:
                count = mid + 1
                left = mid + 1
            else:
                right = mid - 1
        return count
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
