---
Difficulty: Medium  
Source: 160 Days of Problem Solving  
Tags:
  - Dynamic Programming
---

# 🚀 _Day 82. Total Decoding Messages_ 🧠

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/batch/gfg-160-problems/track/dynamic-programming-gfg-160/problem/total-decoding-messages1235)  

## **Problem Description**  

A message containing letters **A-Z** is encoded using the following mapping:  


## Code(C++)
```cpp
class Solution {
public:
    int countWays(string &s) {
        if (s[0] == '0') return 0;
        int n = s.size(), prev2 = 1, prev1 = 1;
        for (int i = 1; i < n; i++) {
            int curr = 0;
            if (s[i] != '0') curr = prev1;
            int num = (s[i - 1] - '0') * 10 + (s[i] - '0');
            if (num >= 10 && num <= 26) curr += prev2;
            prev2 = prev1;
            prev1 = curr;
        }
        return prev1;
    }
};
```

## Code (Java)

```java
class Solution {
    public int countWays(String s) {
        if (s.charAt(0) == '0') return 0;
        int prev2 = 1, prev1 = 1;
        for (int i = 1; i < s.length(); i++) {
            int curr = (s.charAt(i) != '0') ? prev1 : 0;
            if (s.charAt(i - 1) != '0' && Integer.parseInt(s.substring(i - 1, i + 1)) <= 26) 
                curr += prev2;
            prev2 = prev1;
            prev1 = curr;
        }
        return prev1;
    }
}
```

## Code (Python)

```python
class Solution:
    def countWays(self, s: str) -> int:
        if s[0] == '0': return 0
        prev2, prev1 = 1, 1
        for i in range(1, len(s)):
            curr = prev1 if s[i] != '0' else 0
            if s[i - 1] != '0' and int(s[i - 1:i + 1]) <= 26:
                curr += prev2
            prev2, prev1 = prev1, curr
        return prev1
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
