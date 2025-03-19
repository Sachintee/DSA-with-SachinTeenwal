--- ❤️ ---

# 🚀 _Day 78. Length of Last Word_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/length-of-last-word/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <string>
using namespace std;

class Solution {
public:
    int lengthOfLastWord(const string &A) {
        int length = 0;
        int i = A.length() - 1;

        // Skip trailing spaces
        while (i >= 0 && A[i] == ' ') {
            i--;
        }

        // Count the length of the last word
        while (i >= 0 && A[i] != ' ') {
            length++;
            i--;
        }

        return length;
    }
};
```

## Code (Java)

```java
public class Solution {
    public int lengthOfLastWord(final String A) {
        int length = 0;
        int i = A.length() - 1;

        // Skip trailing spaces
        while (i >= 0 && A.charAt(i) == ' ') {
            i--;
        }

        // Count the length of the last word
        while (i >= 0 && A.charAt(i) != ' ') {
            length++;
            i--;
        }

        return length;
    }
}
```

## Code (Python)

```python
class Solution:
    def lengthOfLastWord(self, A):
        # Initialize the length counter
        length = 0
        
        # Start from the end of the string
        i = len(A) - 1
        
        # Skip trailing spaces
        while i >= 0 and A[i] == ' ':
            i -= 1
        
        # Count the length of the last word
        while i >= 0 and A[i] != ' ':
            length += 1
            i -= 1
        
        return length
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
