--- ❤️ ---

# 🚀 _Day 227. Longest valid Parentheses_ 🧠


The problem can be found at the following link: [Problem Link](https://www.interviewbit.com/problems/longest-valid-parentheses/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
#include <stack>
#include <algorithm>

using namespace std;

class Solution {
public:
    int longestValidParentheses(string A) {
        stack<int> st;
        st.push(-1);
        int max_len = 0;
        for (int i = 0; i < A.size(); ++i) {
            if (A[i] == '(') {
                st.push(i);
            } else {
                st.pop();
                if (st.empty()) {
                    st.push(i);
                } else {
                    int current_len = i - st.top();
                    max_len = max(max_len, current_len);
                }
            }
        }
        return max_len;
    }
};
```

## Code (Java)

```java
import java.util.Stack;

public class Solution {
    public int longestValidParentheses(String A) {
        Stack<Integer> stack = new Stack<>();
        stack.push(-1);
        int max_len = 0;
        for (int i = 0; i < A.length(); ++i) {
            if (A.charAt(i) == '(') {
                stack.push(i);
            } else {
                stack.pop();
                if (stack.isEmpty()) {
                    stack.push(i);
                } else {
                    int current_len = i - stack.peek();
                    max_len = Math.max(max_len, current_len);
                }
            }
        }
        return max_len;
    }
}
```

## Code (Python)

```python
class Solution:
    def longestValidParentheses(self, A):
        stack = [-1]
        max_len = 0
        for i in range(len(A)):
            if A[i] == '(':
                stack.append(i)
            else:
                stack.pop()
                if not stack:
                    stack.append(i)
                else:
                    current_len = i - stack[-1]
                    if current_len > max_len:
                        max_len = current_len
        return max_len
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
