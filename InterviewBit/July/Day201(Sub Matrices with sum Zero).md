--- ❤️ ---

# 🚀 _Day 201. Sub Matrices with sum Zero_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/sub-matrices-with-sum-zero/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <unordered_map>
using namespace std;

class Solution {
public:
    int solve(vector<vector<int>> &A) {
        int n = A.size(), m = A[0].size();
        int count = 0;

        for (int top = 0; top < n; ++top) {
            vector<int> temp(m, 0);

            for (int bottom = top; bottom < n; ++bottom) {
                // Compress rows between top and bottom
                for (int col = 0; col < m; ++col) {
                    temp[col] += A[bottom][col];
                }

                unordered_map<int, int> freq;
                freq[0] = 1;
                int prefix_sum = 0;

                for (int val : temp) {
                    prefix_sum += val;
                    count += freq[prefix_sum];
                    freq[prefix_sum]++;
                }
            }
        }

        return count;
    }
};

```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public int solve(int[][] A) {
        int n = A.length, m = A[0].length;
        int count = 0;

        for (int top = 0; top < n; top++) {
            int[] temp = new int[m];

            for (int bottom = top; bottom < n; bottom++) {
                // Compress rows between top and bottom
                for (int col = 0; col < m; col++) {
                    temp[col] += A[bottom][col];
                }

                Map<Integer, Integer> freq = new HashMap<>();
                freq.put(0, 1);
                int prefix_sum = 0;

                for (int val : temp) {
                    prefix_sum += val;
                    count += freq.getOrDefault(prefix_sum, 0);
                    freq.put(prefix_sum, freq.getOrDefault(prefix_sum, 0) + 1);
                }
            }
        }

        return count;
    }
}

```

## Code (Python3)

```python3
class Solution:
    # @param A : list of list of integers
    # @return an integer
    def solve(self, A):
        from collections import defaultdict

        n = len(A)
        m = len(A[0])
        count = 0

        # Loop over all pairs of rows
        for top in range(n):
            temp = [0] * m
            for bottom in range(top, n):
                # Compress rows between top and bottom into temp[]
                for col in range(m):
                    temp[col] += A[bottom][col]

                # Now find number of subarrays with sum = 0 in temp[]
                prefix_sum = 0
                freq = defaultdict(int)
                freq[0] = 1

                for val in temp:
                    prefix_sum += val
                    count += freq[prefix_sum]
                    freq[prefix_sum] += 1

        return count

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
