--- ❤️ ---

# 🚀 _Day 32. Palindrome Integer_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/palindrome-integer/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
using namespace std;

class Solution {
public:
    int isPalindrome(int A) {
        if (A < 0) return 0; // Negative numbers are not palindromes

        long long original = A, reversedNum = 0;
        
        while (A > 0) {
            reversedNum = reversedNum * 10 + A % 10;
            A /= 10;
        }
        
        return (original == reversedNum) ? 1 : 0;
    }
};

// Driver Code
int main() {
    Solution obj;
    cout << obj.isPalindrome(12121) << endl; // Output: 1
    cout << obj.isPalindrome(123) << endl;   // Output: 0
    return 0;
}

```

## Code (Java)

```java
class Solution {
    public int isPalindrome(int A) {
        if (A < 0) return 0; // Negative numbers are not palindromes

        int original = A, reversedNum = 0;
        
        while (A > 0) {
            reversedNum = reversedNum * 10 + A % 10;
            A /= 10;
        }
        
        return (original == reversedNum) ? 1 : 0;
    }

    public static void main(String[] args) {
        Solution obj = new Solution();
        System.out.println(obj.isPalindrome(12121)); // Output: 1
        System.out.println(obj.isPalindrome(123));   // Output: 0
    }
}

```

## Code (Python)

```python
class Solution:
    def isPalindrome(self, A: int) -> int:
        if A < 0:
            return 0  # Negative numbers are not palindromes
        
        original = A
        reversed_num = 0
        
        while A > 0:
            reversed_num = reversed_num * 10 + A % 10
            A //= 10
        
        return 1 if original == reversed_num else 0

```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
