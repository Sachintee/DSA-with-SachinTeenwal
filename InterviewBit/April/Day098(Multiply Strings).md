--- ❤️ ---

# 🚀 _Day 98. Multiply Strings_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/multiply-strings/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <string>
using namespace std;

class Solution {
public:
    string multiply(string num1, string num2) {
        if (num1 == "0" || num2 == "0") {
            return "0";
        }
        
        int len1 = num1.size();
        int len2 = num2.size();
        vector<int> result(len1 + len2, 0);
        
        for (int i = len1 - 1; i >= 0; --i) {
            for (int j = len2 - 1; j >= 0; --j) {
                int product = (num1[i] - '0') * (num2[j] - '0');
                int sum = product + result[i + j + 1];
                result[i + j + 1] = sum % 10;
                result[i + j] += sum / 10;
            }
        }
        
        int start = 0;
        while (start < result.size() && result[start] == 0) {
            ++start;
        }
        
        string res;
        for (int i = start; i < result.size(); ++i) {
            res += to_string(result[i]);
        }
        
        return res;
    }
};
```

## Code (Java)

```java
public class Solution {
    public String multiply(String num1, String num2) {
        if (num1.equals("0") || num2.equals("0")) {
            return "0";
        }
        
        int len1 = num1.length();
        int len2 = num2.length();
        int[] result = new int[len1 + len2];
        
        for (int i = len1 - 1; i >= 0; i--) {
            for (int j = len2 - 1; j >= 0; j--) {
                int product = (num1.charAt(i) - '0') * (num2.charAt(j) - '0');
                int sum = product + result[i + j + 1];
                result[i + j + 1] = sum % 10;
                result[i + j] += sum / 10;
            }
        }
        
        StringBuilder sb = new StringBuilder();
        int start = 0;
        while (start < result.length && result[start] == 0) {
            start++;
        }
        
        for (int i = start; i < result.length; i++) {
            sb.append(result[i]);
        }
        
        return sb.toString();
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : string
    # @param B : string
    # @return a strings
    def multiply(self, A, B):
        if A == "0" or B == "0":
            return "0"
        
        lenA = len(A)
        lenB = len(B)
        result = [0] * (lenA + lenB)
        
        # Multiply each digit of A with each digit of B
        for i in range(lenA - 1, -1, -1):
            for j in range(lenB - 1, -1, -1):
                product = (ord(A[i]) - ord('0')) * (ord(B[j]) - ord('0'))
                total = product + result[i + j + 1]
                result[i + j + 1] = total % 10
                result[i + j] += total // 10
        
        # Convert the result array to a string, skipping leading zeros
        start = 0
        while start < len(result) and result[start] == 0:
            start += 1
        
        result_str = ''.join(map(str, result[start:]))
        return result_str
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
