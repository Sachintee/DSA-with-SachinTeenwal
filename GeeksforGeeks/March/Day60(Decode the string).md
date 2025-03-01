---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Stack
  - Recursion
  - Backtracking
---

# 🚀 _Day 60. Decode the string_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/decode-the-string2444/1)  

## 💡 **Problem Description:**

Given an encoded string `s`, the task is to decode it.  
The encoding rule is:


## Code(C++)
```cpp
class Solution {
public:
    string decodedString(string &s) {
        stack<string> str;
        stack<int> num;
        string cur = "", temp;
        int n = 0;

        for (char c : s) {
            if (isdigit(c)) n = n * 10 + (c - '0');
            else if (c == '[') { str.push(cur); num.push(n); cur = ""; n = 0; }
            else if (c == ']') {
                temp = cur;
                cur = str.top(); str.pop();
                for (int i = 0, x = num.top(); i < x; i++) cur += temp;
                num.pop();
            } else cur += c;
        }
        return cur;
    }
};
```

## Code (Java)

```java
class Solution {
    static String decodeString(String s) {
        Stack<String> str = new Stack<>();
        Stack<Integer> num = new Stack<>();
        String cur = "";
        int n = 0;

        for (char c : s.toCharArray()) {
            if (Character.isDigit(c)) n = n * 10 + (c - '0');
            else if (c == '[') { str.push(cur); num.push(n); cur = ""; n = 0; }
            else if (c == ']') {
                String temp = cur;
                cur = str.pop();
                cur += temp.repeat(num.pop());
            } else cur += c;
        }
        return cur;
    }
}
```

## Code (Python)

```python
class Solution:
    def decodedString(self, s: str) -> str:
        str_st, num_st, cur, n = [], [], "", 0

        for c in s:
            if c.isdigit():
                n = n * 10 + int(c)
            elif c == "[":
                str_st.append(cur)
                num_st.append(n)
                cur, n = "", 0
            elif c == "]":
                cur = str_st.pop() + cur * num_st.pop()
            else:
                cur += c
        return cur
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
