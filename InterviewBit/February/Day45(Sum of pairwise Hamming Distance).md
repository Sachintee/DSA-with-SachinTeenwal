--- ❤️ ---

# 🚀 _Day 45. Sum of pairwise Hamming Distance_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/sum-of-pairwise-hamming-distance/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <algorithm>

using namespace std;

class Solution {
public:
    int hammingDistance(vector<int> &A) {
        const int MOD = 1000000007;
        int n = A.size();
        long long total = 0;

        // Iterate over each bit position (0 to 30, since A[i] <= 10^9)
        for (int i = 0; i < 31; i++) {
            int count = 0;
            for (int num : A) {
                if ((num >> i) & 1) {
                    count++;
                }
            }
            // Number of pairs with different bits at this position
            total = (total + (long long)count * (n - count) * 2) % MOD;
        }

        return (int)total;
    }
};

// Example usage
int main() {
    Solution sol;
    vector<int> A1 = {1};
    cout << sol.hammingDistance(A1) << endl; // Output: 0

    vector<int> A2 = {2, 4, 6};
    cout << sol.hammingDistance(A2) << endl; // Output: 8

    vector<int> A3 = {1, 3, 5};
    cout << sol.hammingDistance(A3) << endl; // Output: 8

    return 0;
}
```

## Code (Java)

```java
import java.util.List;

public class Solution {
    public int hammingDistance(final List<Integer> A) {
        final int MOD = 1000000007;
        int n = A.size();
        long total = 0;

        // Iterate over each bit position (0 to 30, since A[i] <= 10^9)
        for (int i = 0; i < 31; i++) {
            int count = 0;
            for (int num : A) {
                if (((num >> i) & 1) == 1) {
                    count++;
                }
            }
            // Number of pairs with different bits at this position
            total = (total + (long)count * (n - count) * 2) % MOD;
        }

        return (int)total;
    }

    // Example usage
    public static void main(String[] args) {
        Solution sol = new Solution();
        System.out.println(sol.hammingDistance(List.of(1)));          // Output: 0
        System.out.println(sol.hammingDistance(List.of(2, 4, 6)));   // Output: 8
        System.out.println(sol.hammingDistance(List.of(1, 3, 5)));   // Output: 8
    }
}
```

## Code (Python)

```python
class Solution:
    def hammingDistance(self, A):
        MOD = 1000000007
        n = len(A)
        total = 0
        
        # Iterate over each bit position (0 to 30, since A[i] <= 10^9)
        for i in range(31):
            count = 0
            for num in A:
                if (num >> i) & 1:
                    count += 1
            # Number of pairs with different bits at this position
            total = (total + count * (n - count) * 2) % MOD
        
        return total
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
