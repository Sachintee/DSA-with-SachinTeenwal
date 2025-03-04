--- ❤️ ---

# 🚀 _Day 63. WoodCutting Made Easy!_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/woodcutting-made-easy/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <algorithm>
using namespace std;

class Solution {
public:
    int solve(vector<int>& A, int B) {
        // Helper function to calculate total wood cut for a given height H
        auto totalWoodCut = [&](int H) {
            long long total = 0;
            for (int height : A) {
                if (height > H) {
                    total += height - H;
                }
            }
            return total;
        };

        int left = 0;
        int right = *max_element(A.begin(), A.end());
        int result = 0;

        // Binary search to find the maximum H
        while (left <= right) {
            int mid = left + (right - left) / 2;
            long long wood = totalWoodCut(mid);
            if (wood >= B) {
                result = mid;  // Update result to the current mid
                left = mid + 1;  // Try a higher H
            } else {
                right = mid - 1;  // Try a lower H
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
    public int solve(ArrayList<Integer> A, int B) {
        // Helper function to calculate total wood cut for a given height H
        java.util.function.Function<Integer, Long> totalWoodCut = (H) -> {
            long total = 0;
            for (int height : A) {
                if (height > H) {
                    total += height - H;
                }
            }
            return total;
        };

        int left = 0;
        int right = Collections.max(A);
        int result = 0;

        // Binary search to find the maximum H
        while (left <= right) {
            int mid = left + (right - left) / 2;
            long wood = totalWoodCut.apply(mid);
            if (wood >= B) {
                result = mid;  // Update result to the current mid
                left = mid + 1;  // Try a higher H
            } else {
                right = mid - 1;  // Try a lower H
            }
        }

        return result;
    }
}
```

## Code (Python)

```python
class Solution:
    def solve(self, A, B):
        def total_wood_cut(H):
            total = 0
            for height in A:
                if height > H:
                    total += height - H
            return total

        left = 0
        right = max(A)
        result = 0

        while left <= right:
            mid = (left + right) // 2
            wood = total_wood_cut(mid)
            if wood >= B:
                result = mid  # Update result to the current mid
                left = mid + 1  # Try a higher H
            else:
                right = mid - 1  # Try a lower H

        return result
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
