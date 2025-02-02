--- ❤️ ---

# 🚀 _Day 33. Verify Prime_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/verify-prime/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <cmath>

using namespace std;

class Solution {
public:
    int isPrime(int A) {
        if (A <= 1) return 0;  // Not prime
        if (A <= 3) return 1;  // 2 and 3 are prime

        if (A % 2 == 0 || A % 3 == 0) return 0;  // Check divisibility by 2 or 3

        for (int i = 5; i * i <= A; i += 6) {
            if (A % i == 0 || A % (i + 2) == 0) return 0;  // Not prime
        }
        
        return 1;  // Prime
    }
};

// Driver Code
int main() {
    Solution obj;
    int num;
    cout << "Enter a number: ";
    cin >> num;
    cout << (obj.isPrime(num) ? "Prime" : "Not Prime") << endl;
    return 0;
}

```

## Code (Java)

```java
import java.util.*;

class Solution {
    public int isPrime(int A) {
        if (A <= 1) return 0;  // Not prime
        if (A <= 3) return 1;  // 2 and 3 are prime

        if (A % 2 == 0 || A % 3 == 0) return 0;  // Check divisibility by 2 or 3

        for (int i = 5; i * i <= A; i += 6) {
            if (A % i == 0 || A % (i + 2) == 0) return 0;  // Not prime
        }
        
        return 1;  // Prime
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Solution obj = new Solution();

        System.out.print("Enter a number: ");
        int num = sc.nextInt();
        System.out.println(obj.isPrime(num) == 1 ? "Prime" : "Not Prime");

        sc.close();
    }
}

```

## Code (Python)

```python
class Solution:
    def isPrime(self, A):
        if A <= 1:
            return 0  # Not prime
        if A <= 3:
            return 1  # 2 and 3 are prime
        
        # Check divisibility by 2 or 3
        if A % 2 == 0 or A % 3 == 0:
            return 0  # Not prime
        
        # Check divisibility from 5 to sqrt(A)
        i = 5
        while i * i <= A:
            if A % i == 0 or A % (i + 2) == 0:
                return 0  # Not prime
            i += 6
        
        return 1  # Prime
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
