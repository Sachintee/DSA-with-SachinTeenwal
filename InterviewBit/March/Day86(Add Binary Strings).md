--- ❤️ ---

# 🚀 _Day 86. Add Binary Strings_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/add-binary-strings/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <algorithm>
#include <string>

using namespace std;

class Solution {
public:
    string addBinary(string A, string B) {
        int i = A.size() - 1;
        int j = B.size() - 1;
        int carry = 0;
        string result;
        
        while (i >= 0 || j >= 0 || carry) {
            int sum = carry;
            if (i >= 0) {
                sum += A[i] - '0';
                i--;
            }
            if (j >= 0) {
                sum += B[j] - '0';
                j--;
            }
            result.push_back((sum % 2) + '0');
            carry = sum / 2;
        }
        
        reverse(result.begin(), result.end());
        return result;
    }
};
```

## Code (Java)

```java
class Solution {
    public String addBinary(String A, String B) {
        int i = A.length() - 1;
        int j = B.length() - 1;
        int carry = 0;
        StringBuilder result = new StringBuilder();
        
        while (i >= 0 || j >= 0 || carry != 0) {
            int sum = carry;
            if (i >= 0) {
                sum += A.charAt(i) - '0';
                i--;
            }
            if (j >= 0) {
                sum += B.charAt(j) - '0';
                j--;
            }
            result.append(sum % 2);
            carry = sum / 2;
        }
        
        return result.reverse().toString();
    }
}
```

## Code (Python)

```python
class Solution:
    def addBinary(self, A, B):
        i = len(A) - 1
        j = len(B) - 1
        carry = 0
        result = []
        
        while i >= 0 or j >= 0 or carry:
            sum_val = carry
            if i >= 0:
                sum_val += int(A[i])
                i -= 1
            if j >= 0:
                sum_val += int(B[j])
                j -= 1
            result.append(str(sum_val % 2))
            carry = sum_val // 2
        
        return ''.join(reversed(result))
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
