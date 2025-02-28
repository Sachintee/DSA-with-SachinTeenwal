--- ❤️ ---

# 🚀 _Day 59. Make equal elements Array_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/make-equal-elements-array/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <unordered_set>
#include <cmath>

using namespace std;

class Solution {
public:
    int solve(vector<int> &A, int B) {
        // Possible target values are A[0] + B, A[0] - B, or A[0]
        unordered_set<int> possibleTargets = {A[0] + B, A[0] - B, A[0]};
        
        // Check each possible target
        for (int target : possibleTargets) {
            bool valid = true;
            for (int num : A) {
                // Check if the element can be made equal to the target
                if (num != target && abs(num - target) != B) {
                    valid = false;
                    break;
                }
            }
            if (valid) {
                return 1;
            }
        }
        
        return 0;
    }
};
```

## Code (Java)

```java
import java.util.HashSet;
import java.util.Set;

public class Solution {
    public int solve(int[] A, int B) {
        // Possible target values are A[0] + B, A[0] - B, or A[0]
        Set<Integer> possibleTargets = new HashSet<>();
        possibleTargets.add(A[0] + B);
        possibleTargets.add(A[0] - B);
        possibleTargets.add(A[0]);
        
        // Check each possible target
        for (int target : possibleTargets) {
            boolean valid = true;
            for (int num : A) {
                // Check if the element can be made equal to the target
                if (num != target && Math.abs(num - target) != B) {
                    valid = false;
                    break;
                }
            }
            if (valid) {
                return 1;
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
        # Possible target values are A[0] + B, A[0] - B, or A[0]
        possible_targets = {A[0] + B, A[0] - B, A[0]}
        
        # Check each possible target
        for target in possible_targets:
            valid = True
            for num in A:
                # Check if the element can be made equal to the target
                if num != target and abs(num - target) != B:
                    valid = False
                    break
            if valid:
                return 1
        
        return 0
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
