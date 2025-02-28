---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Stack
---

# 🚀 _Day 59. Evaluation of Postfix Expression_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/stack-gfg-160/problem/evaluation-of-postfix-expression1735)  


## 💡 **Problem Description:**

You are given an array of strings `arr` that represents a valid arithmetic expression written in **Reverse Polish Notation (Postfix Notation)**.  

Your task is to evaluate the expression and return an integer representing its value.


## Code(C++)
```cpp
class Solution {
public:
    int evaluate(vector<string>& arr) {
        stack<int> st;
        for (auto &s : arr) {
            if (s == "+" || s == "-" || s == "*" || s == "/") {
                int b = st.top(); st.pop();
                int a = st.top(); st.pop();
                if (s == "+") st.push(a + b);
                else if (s == "-") st.push(a - b);
                else if (s == "*") st.push(a * b);
                else st.push(a / b);
            } else st.push(stoi(s));
        }
        return st.top();
    }
};
```

## Code (Java)

```java
class Solution {
    public int evaluate(String[] arr) {
        Stack<Integer> st = new Stack<>();
        for (String s : arr) {
            if ("+-*/".contains(s)) {
                int b = st.pop(), a = st.pop();
                if (s.equals("+")) st.push(a + b);
                else if (s.equals("-")) st.push(a - b);
                else if (s.equals("*")) st.push(a * b);
                else st.push(a / b);
            } else {
                st.push(Integer.parseInt(s));
            }
        }
        return st.peek();
    }
}
```

## Code (Python)

```python
class Solution:
    def evaluate(self, arr):
        st = []
        for s in arr:
            if s in {"+", "-", "*", "/"}:
                b, a = st.pop(), st.pop()
                if s == "+": st.append(a + b)
                elif s == "-": st.append(a - b)
                elif s == "*": st.append(a * b)
                else: st.append(int(a / b))
            else:
                st.append(int(s))
        return st[-1]
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
