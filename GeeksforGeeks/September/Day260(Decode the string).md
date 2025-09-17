---
title: "🔢 Decode the String | GFG Solution 🔍"
keywords🏷️: ["🔢 string decoding", "🔍 stack", "📍 bracket matching", "📈 nested structures", "📘 GFG", "🏁 competitive programming", "📚 DSA"]
description: "✅ GFG solution to the Decode the String problem: expand encoded patterns k[substring] using stack-based approach for nested bracket handling. 🚀"
date: 📅 2025-09-17
---

# *260. Decode the String*

The problem can be found at the following link: 🔗 [Question Link](https://www.geeksforgeeks.org/problems/decode-the-string2444/1)

## **🧩 Problem Description**

Given an encoded string `s`, decode it by expanding the pattern `k[substring]`, where the substring inside brackets is written `k` times. `k` is guaranteed to be a positive integer, and the encoded string contains only lowercase English alphabets and digits. Return the final decoded string.

The test cases are generated so that the length of the output string will never exceed $10^5$.


## Code(C++)
```cpp
class Solution {
public:
    string decodedString(string& s) {
        stack<pair<string, int>> st;
        string curr = "";
        int num = 0;
        
        for (char c : s) {
            if (isdigit(c)) {
                num = num * 10 + (c - '0');
            } else if (c == '[') {
                st.push({curr, num});
                curr = "";
                num = 0;
            } else if (c == ']') {
                auto [prev, cnt] = st.top();
                st.pop();
                string temp = curr;
                for (int i = 1; i < cnt; i++) curr += temp;
                curr = prev + curr;
            } else {
                curr += c;
            }
        }
        return curr;
    }
};
```

## Code (Java)

```java
class Solution {
    static String decodeString(String s) {
        Stack<StringBuilder> stStr = new Stack<>();
        Stack<Integer> stNum = new Stack<>();
        StringBuilder curr = new StringBuilder();
        int num = 0;
        
        for (char c : s.toCharArray()) {
            if (Character.isDigit(c)) {
                num = num * 10 + (c - '0');
            } else if (c == '[') {
                stStr.push(curr);
                stNum.push(num);
                curr = new StringBuilder();
                num = 0;
            } else if (c == ']') {
                StringBuilder temp = curr;
                curr = stStr.pop();
                int cnt = stNum.pop();
                while (cnt-- > 0) curr.append(temp);
            } else {
                curr.append(c);
            }
        }
        return curr.toString();
    }
}
```

## Code (Python)

```python
class Solution:
    def decodedString(self, s):
        st_str, st_num = [], []
        curr, num = "", 0
        
        for c in s:
            if c.isdigit():
                num = num * 10 + int(c)
            elif c == '[':
                st_str.append(curr)
                st_num.append(num)
                curr, num = "", 0
            elif c == ']':
                temp = curr
                curr = st_str.pop()
                cnt = st_num.pop()
                curr += temp * cnt
            else:
                curr += c
        return curr
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
