--- ❤️ ---

# 🚀 _Day 150. Evaluate Expression_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/evaluate-expression/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <vector>
#include <string>
#include <stack>
#include <cctype>

using namespace std;

class Solution {
public:
    int evalRPN(vector<string>& A) {
        stack<int> stack;
        for (const string& token : A) {
            if (token == "+" || token == "-" || token == "*" || token == "/") {
                int b = stack.top(); stack.pop();
                int a = stack.top(); stack.pop();
                if (token == "+") {
                    stack.push(a + b);
                } else if (token == "-") {
                    stack.push(a - b);
                } else if (token == "*") {
                    stack.push(a * b);
                } else if (token == "/") {
                    stack.push(a / b);
                }
            } else {
                stack.push(stoi(token));
            }
        }
        return stack.top();
    }
};
```

## Code (Java)

```java
import java.util.Stack;

public class Solution {
    public int evalRPN(String[] A) {
        Stack<Integer> stack = new Stack<>();
        for (String token : A) {
            if (token.equals("+") || token.equals("-") || token.equals("*") || token.equals("/")) {
                int b = stack.pop();
                int a = stack.pop();
                switch (token) {
                    case "+":
                        stack.push(a + b);
                        break;
                    case "-":
                        stack.push(a - b);
                        break;
                    case "*":
                        stack.push(a * b);
                        break;
                    case "/":
                        stack.push(a / b);
                        break;
                }
            } else {
                stack.push(Integer.parseInt(token));
            }
        }
        return stack.pop();
    }
}
```

## Code (Python)

```python
class Solution:
    # @param A : list of strings
    # @return an integer
    def evalRPN(self, A):
        stack = []
        for token in A:
            if token in '+-*/':
                b = stack.pop()
                a = stack.pop()
                if token == '+':
                    stack.append(a + b)
                elif token == '-':
                    stack.append(a - b)
                elif token == '*':
                    stack.append(a * b)
                elif token == '/':
                    stack.append(a // b)
            else:
                stack.append(int(token))
        return stack.pop()
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
