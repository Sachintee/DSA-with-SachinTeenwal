--- ❤️ ---

# 🚀 _Day 41. Clear Digits_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/clear-digits/description/?envType=daily-question&envId=2025-02-10)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    string clearDigits(string s) {
        string stk;
        for (char c : s) {
            if (isdigit(c)) {
                stk.pop_back();
            } else {
                stk.push_back(c);
            }
        }
        return stk;
    }
};
```

## Code (Java)

```java
class Solution {
    public String clearDigits(String s) {
        StringBuilder stk = new StringBuilder();
        for (char c : s.toCharArray()) {
            if (Character.isDigit(c)) {
                stk.deleteCharAt(stk.length() - 1);
            } else {
                stk.append(c);
            }
        }
        return stk.toString();
    }
}
```

## Code (Python)

```python
class Solution:
    def clearDigits(self, s: str) -> str:
        stk = []
        for c in s:
            if c.isdigit():
                stk.pop()
            else:
                stk.append(c)
        return "".join(stk)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
