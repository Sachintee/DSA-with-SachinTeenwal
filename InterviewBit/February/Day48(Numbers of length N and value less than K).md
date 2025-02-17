--- ❤️ ---

# 🚀 _Day 48. Numbers of length N and value less than K_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/numbers-of-length-n-and-value-less-than-k/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <bits/stdc++.h>
using namespace std;

class Solution {
public:
    int solve(vector<int> &A, int B, int C) {
        string C_str = to_string(C);
        int C_len = C_str.length();
        int A_size = A.size();
        
        // If A is empty, no numbers can be formed
        if (A_size == 0) return 0;
        
        // If B is greater than the number of digits in C, return 0
        if (B > C_len) return 0;
        
        // If B is smaller, return all possible B-digit numbers
        if (B < C_len) {
            if (A[0] == 0 && B > 1) return (A_size - 1) * pow(A_size, B - 1);
            return pow(A_size, B);
        }

        // When B == C_len, we compare digit by digit
        int count = 0;
        for (int i = 0; i < B; i++) {
            int digit = C_str[i] - '0';

            // Count numbers with a smaller first digit
            int num_smaller = lower_bound(A.begin(), A.end(), digit) - A.begin();
            
            // Don't allow leading zero if B > 1
            if (i == 0 && A[0] == 0 && B > 1) num_smaller--;

            count += num_smaller * pow(A_size, B - 1 - i);

            // If digit not found in A, stop further processing
            if (find(A.begin(), A.end(), digit) == A.end()) break;
        }
        
        return count;
    }
};

int main() {
    Solution sol;
    vector<int> A1 = {0, 1, 5};
    vector<int> A2 = {0, 1, 2, 5};
    
    cout << sol.solve(A1, 1, 2) << endl;  // Output: 2
    cout << sol.solve(A2, 2, 21) << endl; // Output: 5
    
    return 0;
}

```

## Code (Java)

```java
import java.util.*;

class Solution {
    public int solve(ArrayList<Integer> A, int B, int C) {
        String C_str = String.valueOf(C);
        int C_len = C_str.length();
        int A_size = A.size();
        
        // If A is empty, no numbers can be formed
        if (A_size == 0) return 0;

        // If B is greater than the number of digits in C, return 0
        if (B > C_len) return 0;

        // If B is smaller, return all possible B-digit numbers
        if (B < C_len) {
            if (A.get(0) == 0 && B > 1) return (A_size - 1) * (int) Math.pow(A_size, B - 1);
            return (int) Math.pow(A_size, B);
        }

        // When B == C_len, compare digit by digit
        int count = 0;
        for (int i = 0; i < B; i++) {
            int digit = C_str.charAt(i) - '0';

            // Count numbers with a smaller first digit
            int num_smaller = 0;
            for (int num : A) {
                if (num < digit) num_smaller++;
                else break;
            }

            // Don't allow leading zero if B > 1
            if (i == 0 && A.get(0) == 0 && B > 1) num_smaller--;

            count += num_smaller * (int) Math.pow(A_size, B - 1 - i);

            // If digit not in A, stop further checking
            if (!A.contains(digit)) break;
        }

        return count;
    }

    public static void main(String[] args) {
        Solution sol = new Solution();
        ArrayList<Integer> A1 = new ArrayList<>(Arrays.asList(0, 1, 5));
        ArrayList<Integer> A2 = new ArrayList<>(Arrays.asList(0, 1, 2, 5));
        
        System.out.println(sol.solve(A1, 1, 2)); // Output: 2
        System.out.println(sol.solve(A2

```

## Code (Python)

```python
from bisect import bisect_left

class Solution:
    def solve(self, A, B, C):
        C_str = str(C)
        C_len = len(C_str)
        A_size = len(A)
        
        # If A is empty, no numbers can be formed
        if A_size == 0:
            return 0
        
        # If B is greater than the number of digits in C, it's impossible to form a valid number
        if B > C_len:
            return 0
        
        # If B is smaller, we can form all B-digit numbers
        if B < C_len:
            # First digit cannot be zero unless B == 1
            if 0 in A and B > 1:
                return (A_size - 1) * (A_size ** (B - 1))
            else:
                return A_size ** B

        # When B == C_len, we need to compare digit by digit
        count = 0
        prefix = 1  # To check valid numbers with a given prefix
        for i in range(B):
            digit = int(C_str[i])
            
            # Count numbers with a smaller first digit than C[i]
            num_smaller = bisect_left(A, digit)
            
            # If first digit, we should not count '0' unless B == 1
            if i == 0 and 0 in A and B > 1:
                num_smaller -= 1

            count += num_smaller * (A_size ** (B - 1 - i))

            # If the digit is not in A, stop searching
            if digit not in A:
                break
        
        return count

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
