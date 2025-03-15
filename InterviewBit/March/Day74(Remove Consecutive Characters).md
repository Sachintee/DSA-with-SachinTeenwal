--- ❤️ ---

# 🚀 _Day 74. Remove Consecutive Characters_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/remove-consecutive-characters/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <string>
#include <vector>
using namespace std;

class Solution {
public:
    string solve(string A, int B) {
        vector<char> result;
        int n = A.length();
        int i = 0;
        while (i < n) {
            char current_char = A[i];
            int count = 1;
            // Count the number of consecutive same characters
            while (i + count < n && A[i + count] == current_char) {
                count++;
            }
            // If the count is not equal to B, add the characters to the result
            if (count != B) {
                for (int j = 0; j < count; j++) {
                    result.push_back(current_char);
                }
            }
            // Move to the next character
            i += count;
        }
        // Convert the result vector to a string
        return string(result.begin(), result.end());
    }
};
```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public String solve(String A, int B) {
        StringBuilder result = new StringBuilder();
        int n = A.length();
        int i = 0;
        while (i < n) {
            char current_char = A.charAt(i);
            int count = 1;
            // Count the number of consecutive same characters
            while (i + count < n && A.charAt(i + count) == current_char) {
                count++;
            }
            // If the count is not equal to B, add the characters to the result
            if (count != B) {
                for (int j = 0; j < count; j++) {
                    result.append(current_char);
                }
            }
            // Move to the next character
            i += count;
        }
        return result.toString();
    }
}
```

## Code (Python)

```python
class Solution:
    def solve(self, A, B):
        result = []
        n = len(A)
        i = 0
        while i < n:
            current_char = A[i]
            count = 1
            # Count the number of consecutive same characters
            while i + count < n and A[i + count] == current_char:
                count += 1
            # If the count is not equal to B, add the characters to the result
            if count != B:
                result.extend([current_char] * count)
            # Move to the next character
            i += count
        return ''.join(result)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
