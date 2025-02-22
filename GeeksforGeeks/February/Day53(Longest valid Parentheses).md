---
Difficulty: Hard  
Source: 160 Days of Problem Solving  
Tags:
  - Strings
  - Dynamic Programming
  - Stack
---

# 🚀 _Day 53. Longest valid Parentheses_ 🧠


The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/stack-gfg-160/problem/longest-valid-parentheses5657)  

## 💡 **Problem Description:**

Given a string **s** consisting of only **'('** and **')'**, find the **length of the longest valid parentheses substring**.  


## Code(C++)
```cpp
class Solution {
public:
    int maxLength(string s) {
        stack<int> st; st.push(-1);
        int m = 0;
        for (int i = 0; i < s.size(); i++)
            if (s[i] == '(') st.push(i);
            else { 
                st.pop(); 
                if (st.empty()) st.push(i); 
                else m = max(m, i - st.top()); 
            }
        return m;
    }
};
```

## Code (Java)

```java
class Solution {
    static int maxLength(String s) {
        java.util.Stack<Integer> st = new java.util.Stack<>();
        st.push(-1);
        int m = 0;
        for (int i = 0; i < s.length(); i++) {
            if (s.charAt(i) == '(') st.push(i);
            else {
                st.pop();
                if (st.empty()) st.push(i);
                else m = Math.max(m, i - st.peek());
            }
        }
        return m;
    }
}
```

## Code (Python)

```python
class Solution:
    def maxLength(self, s):
        st=[-1]; m=0
        for i,c in enumerate(s):
            if c=='(':
                st.append(i)
            else:
                st.pop()
                if not st: st.append(i)
                else: m = max(m, i - st[-1])
        return m
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
