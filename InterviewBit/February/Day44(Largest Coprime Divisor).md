--- ❤️ ---

# 🚀 _Day 44. Largest Coprime Divisor_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/largest-coprime-divisor/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <algorithm>
#include <iostream>

using namespace std;

class Solution {
public:
    int gcd(int a, int b) {
        while (b != 0) {
            int temp = b;
            b = a % b;
            a = temp;
        }
        return a;
    }

    int cpFact(int A, int B) {
        while (gcd(A, B) != 1) {
            A = A / gcd(A, B);
        }
        return A;
    }
};

// Example usage
int main() {
    Solution sol;
    cout << sol.cpFact(30, 12) << endl; // Output: 5
    cout << sol.cpFact(15, 5) << endl;  // Output: 3
    return 0;
}
```

## Code (Java)

```java
public class Solution {
    private int gcd(int a, int b) {
        while (b != 0) {
            int temp = b;
            b = a % b;
            a = temp;
        }
        return a;
    }

    public int cpFact(int A, int B) {
        while (gcd(A, B) != 1) {
            A = A / gcd(A, B);
        }
        return A;
    }

    // Example usage
    public static void main(String[] args) {
        Solution sol = new Solution();
        System.out.println(sol.cpFact(30, 12)); // Output: 5
        System.out.println(sol.cpFact(15, 5));  // Output: 3
    }
}
```

## Code (Python)

```python
import math

class Solution:
    def cpFact(self, A, B):
        while math.gcd(A, B) != 1:
            A = A // math.gcd(A, B)
        return A
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
