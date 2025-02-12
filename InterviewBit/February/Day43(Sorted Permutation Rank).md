--- ❤️ ---

# 🚀 _Day 43. Sorted Permutation Rank_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/sorted-permutation-rank/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <string>
#include <vector>
#include <algorithm>

using namespace std;

class Solution {
public:
    int factorial(int n, int mod) {
        long long fact = 1;
        for (int i = 1; i <= n; i++) {
            fact = (fact * i) % mod;
        }
        return fact;
    }

    int findRank(string A) {
        const int mod = 1000003;
        int n = A.length();
        long long rank = 1;

        for (int i = 0; i < n; i++) {
            int count = 0;
            for (int j = i + 1; j < n; j++) {
                if (A[j] < A[i]) {
                    count++;
                }
            }
            rank = (rank + count * factorial(n - i - 1, mod)) % mod;
        }

        return rank;
    }
};

// Example usage
int main() {
    Solution sol;
    cout << sol.findRank("acb") << endl; // Output: 2
    cout << sol.findRank("a") << endl;   // Output: 1
    cout << sol.findRank("ba") << endl;  // Output: 2
    cout << sol.findRank("cba") << endl; // Output: 6
    return 0;
}
```

## Code (Java)

```java
public class Solution {
    private int factorial(int n, int mod) {
        long fact = 1;
        for (int i = 1; i <= n; i++) {
            fact = (fact * i) % mod;
        }
        return (int) fact;
    }

    public int findRank(String A) {
        int mod = 1000003;
        int n = A.length();
        long rank = 1;

        for (int i = 0; i < n; i++) {
            int count = 0;
            for (int j = i + 1; j < n; j++) {
                if (A.charAt(j) < A.charAt(i)) {
                    count++;
                }
            }
            rank = (rank + count * factorial(n - i - 1, mod)) % mod;
        }

        return (int) rank;
    }

    // Example usage
    public static void main(String[] args) {
        Solution sol = new Solution();
        System.out.println(sol.findRank("acb")); // Output: 2
        System.out.println(sol.findRank("a"));   // Output: 1
        System.out.println(sol.findRank("ba"));  // Output: 2
        System.out.println(sol.findRank("cba")); // Output: 6
    }
}
```

## Code (Python)

```python
class Solution:
    def factorial(self, n, mod):
        fact = 1
        for i in range(1, n + 1):
            fact = (fact * i) % mod
        return fact

    def findRank(self, A):
        mod = 1000003
        n = len(A)
        rank = 1
        for i in range(n):
            count = 0
            for j in range(i + 1, n):
                if A[j] < A[i]:
                    count += 1
            rank = (rank + count * self.factorial(n - i - 1, mod)) % mod
        return rank
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
