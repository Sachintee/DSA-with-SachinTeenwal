---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Recursion
  - Backtracking
---

# 🚀 _Day 29. Implement Pow_ 🧠


The problem can be found at the following link: [Problem Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/recursion-and-backtracking-gfg-160/problem/powx-n)

## 💡 **Problem Description:**

You are given a floating point number `b` and an integer `e`, and your task is to calculate \( b^e \) (b raised to the power of e).

## Code(C++)
```cpp
#include <iostream>
using namespace std;

class Solution {
public:
    double power(double b, int e) {
        double result = 1.0;
        long long exponent = abs(e); // Use long long to avoid overflow
        
        while (exponent > 0) {
            if (exponent % 2 == 1) {
                result *= b;
            }
            b *= b;
            exponent /= 2;
        }
        
        return (e >= 0) ? result : (1.0 / result);
    }
};

// Driver Code
int main() {
    Solution obj;
    int T;
    cin >> T; // Number of test cases

    while (T--) {
        double b;
        int e;
        cin >> b >> e;
        cout.precision(5);
        cout << fixed << obj.power(b, e) << endl; // Print result with 5 decimal places
    }

    return 0;
}

```

## Code (Java)

```java
import java.util.Scanner;

class Solution {
    public double power(double b, int e) {
        double result = 1.0;
        long exponent = Math.abs((long)e); // Handle edge cases for negative exponents

        while (exponent > 0) {
            if (exponent % 2 == 1) {
                result *= b;
            }
            b *= b;
            exponent /= 2;
        }

        return (e >= 0) ? result : (1.0 / result);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int T = sc.nextInt(); // Number of test cases

        Solution obj = new Solution();

        while (T-- > 0) {
            double b = sc.nextDouble();
            int e = sc.nextInt();
            System.out.printf("%.5f%n", obj.power(b, e)); // Print with 5 decimal precision
        }

        sc.close();
    }
}

```

## Code (Python)

```python
class Solution:
    def power(self, b: float, e: int) -> float:
        result = 1.0
        exponent = abs(e)
        
        while exponent > 0:
            if exponent % 2 == 1:
                result *= b
            b *= b
            exponent //= 2
        
        return result if e >= 0 else 1 / result

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
 <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>983</h4>
