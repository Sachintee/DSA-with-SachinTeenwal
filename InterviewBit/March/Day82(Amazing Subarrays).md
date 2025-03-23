--- ❤️ ---

# 🚀 _Day 82. Amazing Subarrays_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/amazing-subarrays/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <string>
#include <unordered_set>
using namespace std;

class Solution {
public:
    int solve(string A) {
        // Set of vowels (both lowercase and uppercase)
        unordered_set<char> vowels = {'a', 'e', 'i', 'o', 'u', 'A', 'E', 'I', 'O', 'U'};
        int n = A.length();
        int count = 0; // To store the total count of amazing substrings

        for (int i = 0; i < n; i++) {
            if (vowels.find(A[i]) != vowels.end()) {
                // Number of substrings starting at position i is (n - i)
                count += (n - i);
            }
        }

        return count % 10003; // Return the result modulo 10003
    }
};

int main() {
    Solution sol;
    cout << sol.solve("ABEC") << endl; // Output: 6
    cout << sol.solve("AEB") << endl;  // Output: 4
    cout << sol.solve("XYZ") << endl;  // Output: 0
    cout << sol.solve("aEiOu") << endl; // Output: 15
    return 0;
}
```

## Code (Java)

```java
import java.util.HashSet;
import java.util.Set;

public class Solution {
    public int solve(String A) {
        // Set of vowels (both lowercase and uppercase)
        Set<Character> vowels = new HashSet<>();
        vowels.add('a');
        vowels.add('e');
        vowels.add('i');
        vowels.add('o');
        vowels.add('u');
        vowels.add('A');
        vowels.add('E');
        vowels.add('I');
        vowels.add('O');
        vowels.add('U');

        int n = A.length();
        int count = 0; // To store the total count of amazing substrings

        for (int i = 0; i < n; i++) {
            if (vowels.contains(A.charAt(i))) {
                // Number of substrings starting at position i is (n - i)
                count += (n - i);
            }
        }

        return count % 10003; // Return the result modulo 10003
    }

    public static void main(String[] args) {
        Solution sol = new Solution();
        System.out.println(sol.solve("ABEC")); // Output: 6
        System.out.println(sol.solve("AEB"));  // Output: 4
        System.out.println(sol.solve("XYZ"));  // Output: 0
        System.out.println(sol.solve("aEiOu")); // Output: 15
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : string
    # @return an integer
    def solve(self, A):
        vowels = set("aeiouAEIOU")  # Set of vowels (both lowercase and uppercase)
        n = len(A)
        count = 0  # To store the total count of amazing substrings

        for i in range(n):
            if A[i] in vowels:
                # Number of substrings starting at position i is (n - i)
                count += (n - i)

        return count % 10003  # Return the result modulo 10003
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
