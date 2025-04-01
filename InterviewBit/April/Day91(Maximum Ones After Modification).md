--- ❤️ ---

# 🚀 _Day 91. Maximum Ones After Modification_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/maximum-ones-after-modification/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <algorithm>

using namespace std;

class Solution {
public:
    int solve(vector<int>& A, int B) {
        int left = 0;
        int max_length = 0;
        int zero_count = 0;
        
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
            
            int current_window_length = right - left + 1;
            if (current_window_length > max_length) {
                max_length = current_window_length;
            }
        }
        
        return max_length;
    }
};
```

## Code (Java)

```java
public class Solution {
    public int solve(int[] A, int B) {
        int left = 0;
        int maxLength = 0;
        int zeroCount = 0;
        
        for (int right = 0; right < A.length; right++) {
            if (A[right] == 0) {
                zeroCount++;
            }
            
            while (zeroCount > B) {
                if (A[left] == 0) {
                    zeroCount--;
                }
                left++;
            }
            
            int currentWindowLength = right - left + 1;
            if (currentWindowLength > maxLength) {
                maxLength = currentWindowLength;
            }
        }
        
        return maxLength;
    }
}
```

## Code (Python)

```python
class Solution:
    def solve(self, A, B):
        left = 0
        max_length = 0
        zero_count = 0
        
        for right in range(len(A)):
            if A[right] == 0:
                zero_count += 1
            
            while zero_count > B:
                if A[left] == 0:
                    zero_count -= 1
                left += 1
            
            current_window_length = right - left + 1
            if current_window_length > max_length:
                max_length = current_window_length
        
        return max_length
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
