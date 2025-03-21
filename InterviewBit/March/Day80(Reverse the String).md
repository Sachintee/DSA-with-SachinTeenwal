--- ❤️ ---

# 🚀 _Day 80. Reverse the String_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/reverse-the-string/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <iostream>
#include <string>
#include <vector>
#include <sstream>
#include <algorithm>

using namespace std;

class Solution {
public:
    string solve(string A) {
        // Step 1: Trim leading and trailing spaces
        A.erase(0, A.find_first_not_of(' ')); // Remove leading spaces
        A.erase(A.find_last_not_of(' ') + 1); // Remove trailing spaces

        // Step 2: Split the string into words
        vector<string> words;
        stringstream ss(A);
        string word;
        while (ss >> word) { // Split by spaces
            words.push_back(word);
        }

        // Step 3: Reverse the list of words
        reverse(words.begin(), words.end());

        // Step 4: Join the words into a single string with single spaces
        string reversedString;
        for (int i = 0; i < words.size(); i++) {
            reversedString += words[i];
            if (i != words.size() - 1) {
                reversedString += " ";
            }
        }

        return reversedString;
    }
};

int main() {
    Solution sol;
    cout << sol.solve("the sky is blue") << endl; // Output: "blue is sky the"
    cout << sol.solve("this is ib") << endl;      // Output: "ib is this"
    return 0;
}
```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public String solve(String A) {
        // Step 1: Trim leading and trailing spaces
        A = A.trim();

        // Step 2: Split the string into words
        String[] words = A.split("\\s+"); // Split by one or more spaces

        // Step 3: Reverse the list of words
        Collections.reverse(Arrays.asList(words));

        // Step 4: Join the words into a single string with single spaces
        StringBuilder reversedString = new StringBuilder();
        for (int i = 0; i < words.length; i++) {
            reversedString.append(words[i]);
            if (i != words.length - 1) {
                reversedString.append(" ");
            }
        }

        return reversedString.toString();
    }

    public static void main(String[] args) {
        Solution sol = new Solution();
        System.out.println(sol.solve("the sky is blue")); // Output: "blue is sky the"
        System.out.println(sol.solve("this is ib"));       // Output: "ib is this"
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : string
    # @return a string
    def solve(self, A):
        # Step 1: Trim leading and trailing spaces
        A = A.strip()
        
        # Step 2: Split the string into words based on spaces
        words = A.split()
        
        # Step 3: Reverse the list of words
        words.reverse()
        
        # Step 4: Join the words into a single string with single spaces
        reversed_string = ' '.join(words)
        
        return reversed_string
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
