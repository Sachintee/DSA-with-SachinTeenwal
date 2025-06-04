--- ❤️ ---

# 🚀 _Day 155. Rain Water Trapped_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/rain-water-trapped/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <algorithm>

using namespace std;

class Solution {
public:
    int trap(vector<int>& A) {
        if (A.empty()) return 0;
        
        int left = 0, right = A.size() - 1;
        int left_max = A[left], right_max = A[right];
        int water = 0;
        
        while (left < right) {
            if (left_max < right_max) {
                left++;
                left_max = max(left_max, A[left]);
                water += left_max - A[left];
            } else {
                right--;
                right_max = max(right_max, A[right]);
                water += right_max - A[right];
            }
        }
        
        return water;
    }
};
```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public int trap(ArrayList<Integer> A) {
        if (A.isEmpty()) return 0;
        
        int left = 0, right = A.size() - 1;
        int left_max = A.get(left), right_max = A.get(right);
        int water = 0;
        
        while (left < right) {
            if (left_max < right_max) {
                left++;
                left_max = Math.max(left_max, A.get(left));
                water += left_max - A.get(left);
            } else {
                right--;
                right_max = Math.max(right_max, A.get(right));
                water += right_max - A.get(right);
            }
        }
        
        return water;
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : tuple of integers
    # @return an integer
    def trap(self, A):
        if not A:
            return 0
        
        left, right = 0, len(A) - 1
        left_max, right_max = A[left], A[right]
        water = 0
        
        while left < right:
            if left_max < right_max:
                left += 1
                left_max = max(left_max, A[left])
                water += left_max - A[left]
            else:
                right -= 1
                right_max = max(right_max, A[right])
                water += right_max - A[right]
        
        return water
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
