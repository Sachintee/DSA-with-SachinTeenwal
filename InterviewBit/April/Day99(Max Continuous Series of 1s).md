--- ❤️ ---

# 🚀 _Day 99. Max Continuous Series of 1s_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/max-continuous-series-of-1s/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
using namespace std;

class Solution {
public:
    vector<int> maxone(vector<int>& A, int B) {
        int left = 0, zero_count = 0;
        int max_length = 0, best_left = 0, best_right = 0;
        
        for (int right = 0; right < A.size(); ++right) {
            if (A[right] == 0) {
                zero_count++;
            }
            
            while (zero_count > B) {
                if (A[left] == 0) {
                    zero_count--;
                }
                left++;
            }
            
            int current_length = right - left + 1;
            if (current_length > max_length) {
                max_length = current_length;
                best_left = left;
                best_right = right;
            }
        }
        
        vector<int> result;
        for (int i = best_left; i <= best_right; ++i) {
            result.push_back(i);
        }
        return result;
    }
};
```

## Code (Java)

```java
import java.util.ArrayList;
import java.util.List;

class Solution {
    public ArrayList<Integer> maxone(ArrayList<Integer> A, int B) {
        int left = 0, zeroCount = 0;
        int maxLength = 0, bestLeft = 0, bestRight = 0;
        
        for (int right = 0; right < A.size(); right++) {
            if (A.get(right) == 0) {
                zeroCount++;
            }
            
            while (zeroCount > B) {
                if (A.get(left) == 0) {
                    zeroCount--;
                }
                left++;
            }
            
            int currentLength = right - left + 1;
            if (currentLength > maxLength) {
                maxLength = currentLength;
                bestLeft = left;
                bestRight = right;
            }
        }
        
        ArrayList<Integer> result = new ArrayList<>();
        for (int i = bestLeft; i <= bestRight; i++) {
            result.add(i);
        }
        return result;
    }
}
```

## Code (Python)

```python
class Solution:
    def maxone(self, A, B):
        left = 0
        zero_count = 0
        max_length = 0
        best_left = 0
        best_right = 0
        
        for right in range(len(A)):
            if A[right] == 0:
                zero_count += 1
            
            while zero_count > B:
                if A[left] == 0:
                    zero_count -= 1
                left += 1
            
            current_length = right - left + 1
            if current_length > max_length:
                max_length = current_length
                best_left = left
                best_right = right
        
        return list(range(best_left, best_right + 1))
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
