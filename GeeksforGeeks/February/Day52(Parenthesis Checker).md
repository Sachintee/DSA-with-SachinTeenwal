---
Difficulty: Easy  
Source: 160 Days of Problem Solving  
Tags:
  - Strings
  - Stack
  - STL
---

# 🚀 _Day 52. Parenthesis Checker_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/stack-gfg-160/problem/parenthesis-checker2744)  

## 💡 **Problem Description:**

Given a string `s`, composed of different combinations of `(`, `)`, `{`, `}`, `[`, `]`, verify the **validity of the arrangement**.  


## Code(C++)
```cpp
class Solution {
  public:
    bool isBalanced(string& s) {
        stack<char> st;
        for (char c : s) {
            if (c == '(' || c == '{' || c == '[') st.push(c);
            else if (st.empty() || abs(st.top() - c) > 2) return false;
            else st.pop();
        }
        return st.empty();
    }
};
```

## Code (Java)

```java
class Solution {
    static boolean isBalanced(String s) {
        Stack<Character> st = new Stack<>();
        for (char c : s.toCharArray()) 
            if ("({[".indexOf(c) >= 0) st.push(c);
            else if (st.isEmpty() || Math.abs(st.peek() - c) > 2) return false;
            else st.pop();
        return st.isEmpty();
    }
}
```

## Code (Python)

```python
class Solution:
    def isBalanced(self, s):
        st = []
        for c in s:
            if c in "({[": st.append(c)
            elif not st or abs(ord(st[-1]) - ord(c)) > 2: return False
            else: st.pop()
        return not st
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
