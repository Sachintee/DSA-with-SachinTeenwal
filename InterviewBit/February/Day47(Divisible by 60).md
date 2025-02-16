--- ❤️ ---

# 🚀 _Day 47. Divisible by 60_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/divisible-by-60/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <vector>
using namespace std;

class Solution {
public:
    int divisibleBy60(vector<int>& A) {
        // If the only digit is 0, return 1 (0 is divisible by 60)
        if (A.size() == 1 && A[0] == 0) return 1;

        bool hasZero = false;
        int evenCount = 0, digitSum = 0;

        for (int num : A) {
            if (num == 0) hasZero = true;
            if (num % 2 == 0) evenCount++;
            digitSum += num;
        }

        // Must contain at least one '0' and another even number
        if (!hasZero || evenCount < 2) return 0;

        // Sum of digits must be divisible by 3
        return (digitSum % 3 == 0) ? 1 : 0;
    }
};

int main() {
    Solution sol;
    vector<int> A1 = {0, 6};
    vector<int> A2 = {2, 3};
    vector<int> A3 = {0};

    cout << sol.divisibleBy60(A1) << endl; // Output: 1
    cout << sol.divisibleBy60(A2) << endl; // Output: 0
    cout << sol.divisibleBy60(A3) << endl; // Output: 1

    return 0;
}

```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public int divisibleBy60(int[] A) {
        // If the only digit is 0, return 1 (0 is divisible by 60)
        if (A.length == 1 && A[0] == 0) return 1;

        boolean hasZero = false;
        int evenCount = 0, digitSum = 0;

        for (int num : A) {
            if (num == 0) hasZero = true;
            if (num % 2 == 0) evenCount++;
            digitSum += num;
        }

        // Must contain at least one '0' and another even number
        if (!hasZero || evenCount < 2) return 0;

        // Sum of digits must be divisible by 3
        return (digitSum % 3 == 0) ? 1 : 0;
    }

    public static void main(String[] args) {
        Solution sol = new Solution();
        int[] A1 = {0, 6};
        int[] A2 = {2, 3};
        int[] A3 = {0};

        System.out.println(sol.divisibleBy60(A1)); // Output: 1
        System.out.println(sol.divisibleBy60(A2)); // Output: 0
        System.out.println(sol.divisibleBy60(A3)); // Output: 1
    }
}

```

## Code (Python)

```python
class Solution:
    # @param A : list of integers
    # @return an integer
    def divisibleBy60(self, A):
        # If the only digit is 0, return 1 (0 is divisible by 60)
        if A == [0]:
            return 1
        
        # Step 1: Check if there's at least one '0'
        if 0 not in A:
            return 0
        
        # Step 2: Check for another even digit apart from 0
        even_count = sum(1 for x in A if x % 2 == 0)
        
        # Step 3: Check if sum of digits is divisible by 3
        digit_sum = sum(A)
        
        # The number must have at least one extra even digit apart from 0
        if even_count < 2:
            return 0
        
        # The sum of digits must be divisible by 3
        return 1 if digit_sum % 3 == 0 else 0

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
