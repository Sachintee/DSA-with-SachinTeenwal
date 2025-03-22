--- ❤️ ---

# 🚀 _Day 81. Convert to Palindrome_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/convert-to-palindrome/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <string>
using namespace std;

class Solution {
public:
    int solve(string A) {
        int left = 0;
        int right = A.length() - 1;

        while (left < right) {
            if (A[left] == A[right]) {
                left++;
                right--;
            } else {
                // Check if removing A[left] or A[right] makes the string a palindrome
                if (isPalindrome(A, left + 1, right)) {
                    return 1;
                }
                if (isPalindrome(A, left, right - 1)) {
                    return 1;
                }
                return 0;
            }
        }

        // If the string is already a palindrome, check if its length is odd
        if (A.length() % 2 == 1) {
            return 1;
        } else {
            return 0;
        }
    }

private:
    bool isPalindrome(string s, int left, int right) {
        while (left < right) {
            if (s[left] != s[right]) {
                return false;
            }
            left++;
            right--;
        }
        return true;
    }
};

int main() {
    Solution sol;
    cout << sol.solve("abcba") << endl;    // Output: 1
    cout << sol.solve("abecbea") << endl; // Output: 0
    cout << sol.solve("abba") << endl;    // Output: 0
    cout << sol.solve("racecar") << endl; // Output: 1
    cout << sol.solve("abca") << endl;    // Output: 1
    return 0;
}
```

## Code (Java)

```java
public class Solution {
    public int solve(String A) {
        int left = 0;
        int right = A.length() - 1;

        while (left < right) {
            if (A.charAt(left) == A.charAt(right)) {
                left++;
                right--;
            } else {
                // Check if removing A.charAt(left) or A.charAt(right) makes the string a palindrome
                if (isPalindrome(A, left + 1, right)) {
                    return 1;
                }
                if (isPalindrome(A, left, right - 1)) {
                    return 1;
                }
                return 0;
            }
        }

        // If the string is already a palindrome, check if its length is odd
        if (A.length() % 2 == 1) {
            return 1;
        } else {
            return 0;
        }
    }

    private boolean isPalindrome(String s, int left, int right) {
        while (left < right) {
            if (s.charAt(left) != s.charAt(right)) {
                return false;
            }
            left++;
            right--;
        }
        return true;
    }

    public static void main(String[] args) {
        Solution sol = new Solution();
        System.out.println(sol.solve("abcba"));    // Output: 1
        System.out.println(sol.solve("abecbea")); // Output: 0
        System.out.println(sol.solve("abba"));    // Output: 0
        System.out.println(sol.solve("racecar")); // Output: 1
        System.out.println(sol.solve("abca"));    // Output: 1
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : string
    # @return an integer
    def solve(self, A):
        def is_palindrome(s, left, right):
            # Helper function to check if a substring is a palindrome
            while left < right:
                if s[left] != s[right]:
                    return False
                left += 1
                right -= 1
            return True

        left = 0
        right = len(A) - 1

        while left < right:
            if A[left] == A[right]:
                left += 1
                right -= 1
            else:
                # Check if removing A[left] or A[right] makes the string a palindrome
                if is_palindrome(A, left + 1, right):
                    return 1
                if is_palindrome(A, left, right - 1):
                    return 1
                return 0

        # If the string is already a palindrome, check if its length is odd
        # (since removing one character from an odd-length palindrome still leaves it as a palindrome)
        if len(A) % 2 == 1:
            return 1
        else:
            return 0
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
