--- ❤️ ---

# 🚀 _Day 293. Find a peak element_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/find-a-peak-element/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
using namespace std;

class Solution {
public:
    int solve(vector<int>& A) {
        int n = A.size();
        int left = 0;
        int right = n - 1;
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            
            // Check if mid is peak
            bool greaterThanLeft = (mid == 0) || (A[mid] >= A[mid - 1]);
            bool greaterThanRight = (mid == n - 1) || (A[mid] >= A[mid + 1]);
            
            if (greaterThanLeft && greaterThanRight) {
                return A[mid];
            }
            // If left neighbor is greater, search in left half
            else if (mid > 0 && A[mid - 1] > A[mid]) {
                right = mid - 1;
            }
            // If right neighbor is greater, search in right half
            else {
                left = mid + 1;
            }
        }
        
        return -1; // This should never be reached as per problem constraints
    }
};
```

## Code (Java)

```java
public class Solution {
    public int solve(ArrayList<Integer> A) {
        int n = A.size();
        int left = 0;
        int right = n - 1;
        
        while (left <= right) {
            int mid = left + (right - left) / 2;
            
            // Check if mid is peak
            boolean greaterThanLeft = (mid == 0) || (A.get(mid) >= A.get(mid - 1));
            boolean greaterThanRight = (mid == n - 1) || (A.get(mid) >= A.get(mid + 1));
            
            if (greaterThanLeft && greaterThanRight) {
                return A.get(mid);
            }
            // If left neighbor is greater, search in left half
            else if (mid > 0 && A.get(mid - 1) > A.get(mid)) {
                right = mid - 1;
            }
            // If right neighbor is greater, search in right half
            else {
                left = mid + 1;
            }
        }
        
        return -1; // This should never be reached as per problem constraints
    }
}
```

## Code (Python)

```python
class Solution:
    def solve(self, A):
        n = len(A)
        left = 0
        right = n - 1
        
        while left <= right:
            mid = left + (right - left) // 2
            
            # Check if mid is peak
            greater_than_left = (mid == 0) or (A[mid] >= A[mid - 1])
            greater_than_right = (mid == n - 1) or (A[mid] >= A[mid + 1])
            
            if greater_than_left and greater_than_right:
                return A[mid]
            # If left neighbor is greater, search in left half
            elif mid > 0 and A[mid - 1] > A[mid]:
                right = mid - 1
            # If right neighbor is greater, search in right half
            else:
                left = mid + 1
        
        return -1  # This should never be reached as per problem constraints
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
