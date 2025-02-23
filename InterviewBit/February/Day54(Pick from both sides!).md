--- ❤️ ---

# 🚀 _Day 54. Pick from both sides!_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/pick-from-both-sides/)

## 🎯 **My Approach:**


## Code(C++)
```cpp

#include <vector>
#include <algorithm>
using namespace std;

class Solution {
public:
    int solve(vector<int>& A, int B) {
        int n = A.size();
        // Calculate the sum of the first B elements
        int current_sum = 0;
        for (int i = 0; i < B; i++) {
            current_sum += A[i];
        }
        int max_sum = current_sum;

        // Use sliding window to try all combinations of picking from left and right
        int left = B - 1;
        int right = n - 1;
        while (left >= 0) {
            current_sum = current_sum - A[left] + A[right];
            max_sum = max(max_sum, current_sum);
            left--;
            right--;
        }

        return max_sum;
    }
};
```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public int solve(ArrayList<Integer> A, int B) {
        int n = A.size();
        // Calculate the sum of the first B elements
        int current_sum = 0;
        for (int i = 0; i < B; i++) {
            current_sum += A.get(i);
        }
        int max_sum = current_sum;

        // Use sliding window to try all combinations of picking from left and right
        int left = B - 1;
        int right = n - 1;
        while (left >= 0) {
            current_sum = current_sum - A.get(left) + A.get(right);
            max_sum = Math.max(max_sum, current_sum);
            left--;
            right--;
        }

        return max_sum;
    }
}
```

## Code (Python)

```python
class Solution:
    def solve(self, A, B):
        n = len(A)
        # Calculate the sum of the first B elements
        current_sum = sum(A[:B])
        max_sum = current_sum
        
        # Use sliding window to try all combinations of picking from left and right
        left = B - 1
        right = n - 1
        while left >= 0:
            current_sum = current_sum - A[left] + A[right]
            max_sum = max(max_sum, current_sum)
            left -= 1
            right -= 1
        
        return max_sum
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
