--- ❤️ ---

# 🚀 _Day 49. Binary Representation_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/binary-representation/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
using namespace std;

class Solution {
public:
    string findDigitsInBinary(int A) {
        if (A == 0) return "0"; // Edge case for 0
        string binary = "";
        while (A > 0) {
            binary = char('0' + (A % 2)) + binary;
            A /= 2;
        }
        return binary;
    }
};

int main() {
    Solution sol;
    cout << sol.findDigitsInBinary(6) << endl;  // Output: "110"
    cout << sol.findDigitsInBinary(0) << endl;  // Output: "0"
    cout << sol.findDigitsInBinary(10) << endl; // Output: "1010"
    return 0;
}

```

## Code (Java)

```java
class Solution {
    public String findDigitsInBinary(int A) {
        if (A == 0) return "0"; // Edge case for 0
        StringBuilder binary = new StringBuilder();
        while (A > 0) {
            binary.insert(0, A % 2); // Append at the beginning
            A /= 2;
        }
        return binary.toString();
    }

    public static void main(String[] args) {
        Solution sol = new Solution();
        System.out.println(sol.findDigitsInBinary(6));  // Output: "110"
        System.out.println(sol.findDigitsInBinary(0));  // Output: "0"
        System.out.println(sol.findDigitsInBinary(10)); // Output: "1010"
    }
}

```

## Code (Python)

```python
class Solution:
    # @param A : integer
    # @return a string
    def findDigitsInBinary(self, A):
        return bin(A)[2:]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
