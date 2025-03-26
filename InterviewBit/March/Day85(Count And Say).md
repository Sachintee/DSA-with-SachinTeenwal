--- ❤️ ---

# 🚀 _Day 85. Count And Say_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/count-and-say/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <string>
#include <vector>

using namespace std;

class Solution {
public:
    string countAndSay(int n) {
        if (n == 1) {
            return "1";
        }
        string previous_term = "1";
        for (int i = 1; i < n; ++i) {
            string next_term;
            int j = 0;
            while (j < previous_term.size()) {
                char current_char = previous_term[j];
                int count = 1;
                while (j + 1 < previous_term.size() && previous_term[j] == previous_term[j + 1]) {
                    ++j;
                    ++count;
                }
                next_term += to_string(count) + current_char;
                ++j;
            }
            previous_term = next_term;
        }
        return previous_term;
    }
};
```

## Code (Java)

```java
class Solution {
    public String countAndSay(int n) {
        if (n == 1) {
            return "1";
        }
        String previousTerm = "1";
        for (int i = 1; i < n; i++) {
            StringBuilder nextTerm = new StringBuilder();
            int j = 0;
            while (j < previousTerm.length()) {
                char currentChar = previousTerm.charAt(j);
                int count = 1;
                while (j + 1 < previousTerm.length() && previousTerm.charAt(j) == previousTerm.charAt(j + 1)) {
                    j++;
                    count++;
                }
                nextTerm.append(count).append(currentChar);
                j++;
            }
            previousTerm = nextTerm.toString();
        }
        return previousTerm;
    }
}
```

## Code (Python)

```python
class Solution:
    def countAndSay(self, A):
        if A == 1:
            return "1"
        previous_term = "1"
        for _ in range(1, A):
            next_term = []
            i = 0
            while i < len(previous_term):
                current_char = previous_term[i]
                count = 1
                while i + 1 < len(previous_term) and previous_term[i] == previous_term[i + 1]:
                    i += 1
                    count += 1
                next_term.append(str(count) + current_char)
                i += 1
            previous_term = ''.join(next_term)
        return previous_term
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
