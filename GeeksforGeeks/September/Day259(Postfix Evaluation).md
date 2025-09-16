---
title: "🧮 Postfix Evaluation | GFG Solution 🔍"
keywords🏷️: ["🧮 postfix evaluation", "🔍 stack", "📊 expression evaluation", "🎯 reverse polish notation", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Postfix Evaluation problem: evaluate arithmetic expressions written in Reverse Polish Notation using stack data structure. 🚀"
date: 📅 2025-09-16
---

# *259. Postfix Evaluation*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/evaluation-of-postfix-expression1735/1)

## **🧩 Problem Description**

You are given an array of strings `arr[]` that represents a valid arithmetic expression written in **Reverse Polish Notation (Postfix Notation)**. Your task is to evaluate the expression and return an integer representing its value.

**Note:** A postfix expression is of the form `operand1 operand2 operator` (e.g., "a b +"). The division operation between two integers always computes the floor value, i.e `floor(5 / 3) = 1` and `floor(-5 / 3) = -2`. It is guaranteed that the result of the expression and all intermediate calculations will fit in a 32-bit signed integer.

## Code(C++)
```cpp
class Solution {
public:
    int evaluatePostfix(vector<string>& arr) {
        stack<int> st;
        for (const auto& t : arr) {
            if (t.size() == 1 && strchr("+-*/^", t[0])) {
                int b = st.top(); st.pop();
                int a = st.top(); st.pop();
                if (t[0] == '/') st.push((a < 0) ^ (b < 0) && a % b ? a / b - 1 : a / b);
                else st.push(t[0] == '+' ? a + b : t[0] == '-' ? a - b : 
                           t[0] == '*' ? a * b : pow(a, b));
            } else st.push(stoi(t));
        }
        return st.top();
    }
};
```

## Code (Java)

```java
class Solution {
    public int evaluatePostfix(String[] arr) {
        Stack<Integer> st = new Stack<>();
        for (String t : arr) {
            if (t.length() == 1 && "+-*/^".contains(t)) {
                int b = st.pop(), a = st.pop();
                if (t.equals("/")) st.push((a < 0) ^ (b < 0) && a % b != 0 ? a / b - 1 : a / b);
                else st.push(t.equals("+") ? a + b : t.equals("-") ? a - b : 
                           t.equals("*") ? a * b : (int)Math.pow(a, b));
            } else st.push(Integer.parseInt(t));
        }
        return st.peek();
    }
}
```

## Code (Python)

```python
class Solution:
    def evaluatePostfix(self, arr):
        st = []
        for t in arr:
            if t in "+-*/^" and len(t) == 1:
                b, a = st.pop(), st.pop()
                if t == '/':
                    st.append(a // b)
                else:
                    st.append(a + b if t == '+' else a - b if t == '-' else 
                             a * b if t == '*' else a ** b)
            else:
                st.append(int(t))
        return st[-1]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
