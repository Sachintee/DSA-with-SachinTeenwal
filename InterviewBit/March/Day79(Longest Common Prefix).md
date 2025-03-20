--- ❤️ ---

# 🚀 _Day 79. Longest Common Prefix_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/longest-common-prefix/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <string>
#include <vector>
#include <algorithm>

using namespace std;

class Solution {
public:
    string longestCommonPrefix(vector<string>& A) {
        if (A.empty()) return "";

        // Find the shortest string in the array
        string shortest = *min_element(A.begin(), A.end(), [](const string& a, const string& b) {
            return a.length() < b.length();
        });

        // Iterate through the characters of the shortest string
        for (int i = 0; i < shortest.length(); i++) {
            char currentChar = shortest[i];
            // Compare the character with the corresponding character in all strings
            for (const string& s : A) {
                if (s[i] != currentChar) {
                    return shortest.substr(0, i);
                }
            }
        }

        // If all characters match, return the shortest string
        return shortest;
    }
};
```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public String longestCommonPrefix(ArrayList<String> A) {
        if (A == null || A.isEmpty()) return "";

        // Find the shortest string in the array
        String shortest = A.get(0);
        for (String s : A) {
            if (s.length() < shortest.length()) {
                shortest = s;
            }
        }

        // Iterate through the characters of the shortest string
        for (int i = 0; i < shortest.length(); i++) {
            char currentChar = shortest.charAt(i);
            // Compare the character with the corresponding character in all strings
            for (String s : A) {
                if (s.charAt(i) != currentChar) {
                    return shortest.substring(0, i);
                }
            }
        }

        // If all characters match, return the shortest string
        return shortest;
    }
}
```

## Code (Python)

```python
class Solution:
    def longestCommonPrefix(self, A):
        if not A:
            return ""
        
        # Find the shortest string in the array
        shortest = min(A, key=len)
        
        # Iterate through the characters of the shortest string
        for i, char in enumerate(shortest):
            # Compare the character with the corresponding character in all strings
            for string in A:
                if string[i] != char:
                    return shortest[:i]
        
        # If all characters match, return the shortest string
        return shortest
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
