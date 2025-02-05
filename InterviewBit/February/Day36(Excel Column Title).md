--- ❤️ ---

# 🚀 _Day 36. Excel Column Title_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/excel-column-title/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <string>
using namespace std;

class Solution {
public:
    string convertToTitle(int A) {
        string result = "";
        while (A > 0) {
            A--;  // Adjust for 1-based indexing
            int remainder = A % 26;
            result = char('A' + remainder) + result;
            A = A / 26;
        }
        return result;
    }
};
```

## Code (Java)

```java
class Solution {
    public String convertToTitle(int A) {
        StringBuilder result = new StringBuilder();
        while (A > 0) {
            A--;  // Adjust for 1-based indexing
            int remainder = A % 26;
            result.insert(0, (char) ('A' + remainder));
            A = A / 26;
        }
        return result.toString();
    }
}
```

## Code (Python)

```python
class Solution:
    def convertToTitle(self, A):
        result = ""
        while A > 0:
            A -= 1  # Adjust for 1-based indexing
            remainder = A % 26
            result = chr(ord('A') + remainder) + result
            A = A // 26
        return result
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
