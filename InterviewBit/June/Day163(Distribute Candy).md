--- ❤️ ---

# 🚀 _Day 163. Distribute Candy_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/distribute-candy/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <numeric>

using namespace std;

class Solution {
public:
    int candy(vector<int>& A) {
        int n = A.size();
        vector<int> candies(n, 1);
        
        // Left to right pass
        for (int i = 1; i < n; ++i) {
            if (A[i] > A[i-1]) {
                candies[i] = candies[i-1] + 1;
            }
        }
        
        // Right to left pass
        for (int i = n-2; i >= 0; --i) {
            if (A[i] > A[i+1] && candies[i] <= candies[i+1]) {
                candies[i] = candies[i+1] + 1;
            }
        }
        
        return accumulate(candies.begin(), candies.end(), 0);
    }
};
```

## Code (Java)

```java
import java.util.Arrays;

class Solution {
    public int candy(int[] A) {
        int n = A.length;
        int[] candies = new int[n];
        Arrays.fill(candies, 1);
        
        // Left to right pass
        for (int i = 1; i < n; ++i) {
            if (A[i] > A[i-1]) {
                candies[i] = candies[i-1] + 1;
            }
        }
        
        // Right to left pass
        for (int i = n-2; i >= 0; --i) {
            if (A[i] > A[i+1] && candies[i] <= candies[i+1]) {
                candies[i] = candies[i+1] + 1;
            }
        }
        
        int total = 0;
        for (int candy : candies) {
            total += candy;
        }
        return total;
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : list of integers
    # @return an integer
    def candy(self, A):
        n = len(A)
        candies = [1] * n
        
        # Left to right pass
        for i in range(1, n):
            if A[i] > A[i-1]:
                candies[i] = candies[i-1] + 1
        
        # Right to left pass
        for i in range(n-2, -1, -1):
            if A[i] > A[i+1] and candies[i] <= candies[i+1]:
                candies[i] = candies[i+1] + 1
        
        return sum(candies)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
