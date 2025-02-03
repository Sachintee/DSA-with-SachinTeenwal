--- ❤️ ---

# 🚀 _Day 34. Excel Column Number_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/excel-column-number/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <string>
using namespace std;

class Solution {
public:
    int titleToNumber(string A) {
        int result = 0;
        for (char ch : A) {
            // Convert character to corresponding value (A=1, B=2, ..., Z=26)
            int value = ch - 'A' + 1;
            // Update result
            result = result * 26 + value;
        }
        return result;
    }
};

// Example usage
int main() {
    Solution solution;
    string input1 = "A";
    string input2 = "AB";
    string input3 = "ZY";

    cout << "Column number for " << input1 << " is: " << solution.titleToNumber(input1) << endl; // Output: 1
    cout << "Column number for " << input2 << " is: " << solution.titleToNumber(input2) << endl; // Output: 28
    cout << "Column number for " << input3 << " is: " << solution.titleToNumber(input3) << endl; // Output: 701

    return 0;
}
```

## Code (Java)

```java
class Solution {
    public int titleToNumber(String A) {
        int result = 0;
        for (int i = 0; i < A.length(); i++) {
            char ch = A.charAt(i);
            // Convert character to corresponding value (A=1, B=2, ..., Z=26)
            int value = ch - 'A' + 1;
            // Update result
            result = result * 26 + value;
        }
        return result;
    }
}

// Example usage
public class Main {
    public static void main(String[] args) {
        Solution solution = new Solution();
        String input1 = "A";
        String input2 = "AB";
        String input3 = "ZY";

        System.out.println("Column number for " + input1 + " is: " + solution.titleToNumber(input1)); // Output: 1
        System.out.println("Column number for " + input2 + " is: " + solution.titleToNumber(input2)); // Output: 28
        System.out.println("Column number for " + input3 + " is: " + solution.titleToNumber(input3)); // Output: 701
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : string
    # @return an integer
    def titleToNumber(self, A):
        result = 0
        for char in A:
            # Convert character to corresponding value (A=1, B=2, ..., Z=26)
            value = ord(char) - ord('A') + 1
            # Update result
            result = result * 26 + value
        return result
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
