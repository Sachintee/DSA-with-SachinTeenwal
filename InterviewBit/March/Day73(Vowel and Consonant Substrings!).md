--- ❤️ ---

# 🚀 _Day 73. Vowel and Consonant Substrings!_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/vowel-and-consonant-substrings/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <string>
#include <unordered_set>
using namespace std;

class Solution {
public:
    int solve(string A) {
        const int MOD = 1e9 + 7;
        unordered_set<char> vowels = {'a', 'e', 'i', 'o', 'u'};
        int n = A.length();
        int vowel_count = 0, consonant_count = 0;
        long long result = 0;

        // Count the total number of vowels and consonants in the string
        for (char ch : A) {
            if (vowels.find(ch) != vowels.end()) {
                vowel_count++;
            } else {
                consonant_count++;
            }
        }

        // Calculate the number of substrings that start with a vowel and end with a consonant or vice versa
        for (char ch : A) {
            if (vowels.find(ch) != vowels.end()) {
                result += consonant_count;
                vowel_count--;
            } else {
                result += vowel_count;
                consonant_count--;
            }
        }

        return result % MOD;
    }
};
```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public int solve(String A) {
        final int MOD = 1000000007;
        Set<Character> vowels = new HashSet<>(Arrays.asList('a', 'e', 'i', 'o', 'u'));
        int n = A.length();
        int vowel_count = 0, consonant_count = 0;
        long result = 0;

        // Count the total number of vowels and consonants in the string
        for (char ch : A.toCharArray()) {
            if (vowels.contains(ch)) {
                vowel_count++;
            } else {
                consonant_count++;
            }
        }

        // Calculate the number of substrings that start with a vowel and end with a consonant or vice versa
        for (char ch : A.toCharArray()) {
            if (vowels.contains(ch)) {
                result += consonant_count;
                vowel_count--;
            } else {
                result += vowel_count;
                consonant_count--;
            }
        }

        return (int)(result % MOD);
    }
}
```

## Code (Python)

```python
class Solution:
    def solve(self, A):
        MOD = 10**9 + 7
        vowels = set(['a', 'e', 'i', 'o', 'u'])
        n = len(A)
        vowel_count = 0
        consonant_count = 0
        result = 0
        
        # Count the total number of vowels and consonants in the string
        for char in A:
            if char in vowels:
                vowel_count += 1
            else:
                consonant_count += 1
        
        # Calculate the number of substrings that start with a vowel and end with a consonant
        for char in A:
            if char in vowels:
                result += consonant_count
                vowel_count -= 1
            else:
                result += vowel_count
                consonant_count -= 1
        
        return result % MOD
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
