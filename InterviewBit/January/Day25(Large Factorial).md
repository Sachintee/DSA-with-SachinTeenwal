
# 🚀 _Day 25. Large Factorial_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/large-factorial/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <string>
using namespace std;

class Solution {
public:
    // @param A : integer
    // @return a string
    string solve(int A) {
        // Initialize the result as 1 (since 0! = 1 and 1! = 1)
        long long result = 1;
        
        // Calculate factorial iteratively
        for (int i = 2; i <= A; i++) {
            result *= i;
        }
        
        // Return the result as a string
        return to_string(result);
    }
};

int main() {
    Solution solution;
    cout << solution.solve(9) << endl;   // Output: "362880"
    cout << solution.solve(2) << endl;   // Output: "2"
    cout << solution.solve(3) << endl;   // Output: "6"
    cout << solution.solve(100) << endl; // Output: Large factorial string
    return 0;
}

```

## Code (Java)

```java
public class Solution {
    // @param A : integer
    // @return a string
    public String solve(int A) {
        // Initialize the result as 1 (since 0! = 1 and 1! = 1)
        long result = 1;
        
        // Calculate factorial iteratively
        for (int i = 2; i <= A; i++) {
            result *= i;
        }
        
        // Return the result as a string
        return Long.toString(result);
    }

    // Example usage
    public static void main(String[] args) {
        Solution solution = new Solution();
        System.out.println(solution.solve(9));   // Output: "362880"
        System.out.println(solution.solve(2));   // Output: "2"
        System.out.println(solution.solve(3));   // Output: "6"
        System.out.println(solution.solve(100)); // Output: Large factorial string
    }
}

```

## Code (Python)

```python
class Solution:
    # @param A : integer
    # @return a string
    def solve(self, A):
        # Initialize the result as 1 (since 0! = 1 and 1! = 1)
        result = 1
        
        # Calculate factorial iteratively
        for i in range(2, A + 1):
            result *= i
        
        # Return the result as a string
        return str(result)

# Example usage:
solution = Solution()
print(solution.solve(9))  # Output: "362880"
print(solution.solve(2))  # Output: "2"
print(solution.solve(3))  # Output: "6"
print(solution.solve(100))  # Output: "933262154439441526816992388562667004907159682643816214685929638952175999932299156089414639761565182862536979208272237582511852109168640000000000000000000000000"
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---

<div align="center">
 <h3><b>❤️Visitor Count❤️</b></h3>
   <textalign="center">
   <h4>635</h4>
