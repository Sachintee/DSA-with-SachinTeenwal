--- ❤️ ---

# 🚀 _Day 89. 3 Sum_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/3-sum/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <algorithm>
#include <climits>

using namespace std;

class Solution {
public:
    int threeSumClosest(vector<int>& A, int B) {
        sort(A.begin(), A.end());
        int n = A.size();
        int closest_sum = INT_MAX;
        
        for (int i = 0; i < n - 2; ++i) {
            int left = i + 1;
            int right = n - 1;
            while (left < right) {
                int current_sum = A[i] + A[left] + A[right];
                if (current_sum == B) {
                    return current_sum;
                }
                if (abs(current_sum - B) < abs(closest_sum - B) || closest_sum == INT_MAX) {
                    closest_sum = current_sum;
                }
                if (current_sum < B) {
                    left++;
                } else {
                    right--;
                }
            }
        }
        return closest_sum;
    }
};
```

## Code (Java)

```java
import java.util.Arrays;

class Solution {
    public int threeSumClosest(int[] A, int B) {
        Arrays.sort(A);
        int n = A.length;
        int closestSum = Integer.MAX_VALUE;
        
        for (int i = 0; i < n - 2; i++) {
            int left = i + 1;
            int right = n - 1;
            while (left < right) {
                int currentSum = A[i] + A[left] + A[right];
                if (currentSum == B) {
                    return currentSum;
                }
                if (Math.abs(currentSum - B) < Math.abs(closestSum - B) || closestSum == Integer.MAX_VALUE) {
                    closestSum = currentSum;
                }
                if (currentSum < B) {
                    left++;
                } else {
                    right--;
                }
            }
        }
        return closestSum;
    }
}
```

## Code (Python)

```python
class Solution:
    def threeSumClosest(self, A, B):
        A.sort()
        n = len(A)
        closest_sum = float('inf')
        
        for i in range(n - 2):
            left = i + 1
            right = n - 1
            while left < right:
                current_sum = A[i] + A[left] + A[right]
                if current_sum == B:
                    return current_sum
                if abs(current_sum - B) < abs(closest_sum - B):
                    closest_sum = current_sum
                if current_sum < B:
                    left += 1
                else:
                    right -= 1
        return closest_sum
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
