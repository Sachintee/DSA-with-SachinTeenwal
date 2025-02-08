--- ❤️ ---

# 🚀 _Day 39. Trailing Zeros in Factorial_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/trailing-zeros-in-factorial/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <bits/stdc++.h>
using namespace std;

class Solution {
public:
    int trailingZeroes(int A) {
        int count = 0;
        while (A >= 5) {
            A /= 5;
            count += A;
        }
        return count;
    }
};

// Driver Code
int main() {
    Solution sol;
    int A = 5;
    cout << sol.trailingZeroes(A) << endl;  // Output: 1
    return 0;
}

```

## Code (Java)

```java
class Solution {
    public int trailingZeroes(int A) {
        int count = 0;
        while (A >= 5) {
            A /= 5;
            count += A;
        }
        return count;
    }

    // Driver Code
    public static void main(String[] args) {
        Solution sol = new Solution();
        int A = 5;
        System.out.println(sol.trailingZeroes(A));  // Output: 1
    }
}

```

## Code (Python)

```python
class Solution:
    # @param A : integer
    # @return an integer
    def trailingZeroes(self, A):
        count = 0
        while A >= 5:
            A //= 5
            count += A
        return count

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
