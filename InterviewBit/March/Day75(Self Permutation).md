--- ❤️ ---

# 🚀 _Day 75. Self Permutation_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/self-permutation/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <string>
#include <unordered_map>
using namespace std;

class Solution {
public:
    int permuteStrings(string A, string B) {
        // If lengths are different, no permutation is possible
        if (A.length() != B.length()) {
            return 0;
        }
        
        // Use a map to count characters in A and B
        unordered_map<char, int> count;
        
        // Count characters in A
        for (char ch : A) {
            count[ch]++;
        }
        
        // Subtract characters in B
        for (char ch : B) {
            count[ch]--;
        }
        
        // Check if all counts are zero
        for (auto& pair : count) {
            if (pair.second != 0) {
                return 0;
            }
        }
        
        return 1;
    }
};
```

## Code (Java)

```java
import java.util.*;

public class Solution {
    public int permuteStrings(String A, String B) {
        // If lengths are different, no permutation is possible
        if (A.length() != B.length()) {
            return 0;
        }
        
        // Use a map to count characters in A and B
        Map<Character, Integer> count = new HashMap<>();
        
        // Count characters in A
        for (char ch : A.toCharArray()) {
            count.put(ch, count.getOrDefault(ch, 0) + 1);
        }
        
        // Subtract characters in B
        for (char ch : B.toCharArray()) {
            count.put(ch, count.getOrDefault(ch, 0) - 1);
        }
        
        // Check if all counts are zero
        for (int val : count.values()) {
            if (val != 0) {
                return 0;
            }
        }
        
        return 1;
    }
}
```

## Code (Python)

```python
class Solution:
    def permuteStrings(self, A, B):
        # If lengths are different, no permutation is possible
        if len(A) != len(B):
            return 0
        
        # Use a dictionary to count characters in A and B
        count = {}
        
        # Count characters in A
        for char in A:
            if char in count:
                count[char] += 1
            else:
                count[char] = 1
        
        # Subtract characters in B
        for char in B:
            if char in count:
                count[char] -= 1
            else:
                return 0
        
        # Check if all counts are zero
        for val in count.values():
            if val != 0:
                return 0
        
        return 1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
