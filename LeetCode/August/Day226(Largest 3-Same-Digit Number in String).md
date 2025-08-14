--- ❤️ ---

# 🚀 _Day 226. Largest 3-Same-Digit Number in String_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/largest-3-same-digit-number-in-string/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    string largestGoodInteger(string num) {
        for (char i = '9'; i >= '0'; --i) {
            string s(3, i);
            if (num.find(s) != string::npos) {
                return s;
            }
        }
        return "";
    }
};
```

## Code (Java)

```java
class Solution {
    public String largestGoodInteger(String num) {
        for (int i = 9; i >= 0; i--) {
            String s = String.valueOf(i).repeat(3);
            if (num.contains(s)) {
                return s;
            }
        }
        return "";
    }
}
```

## Code (Python)

```python
class Solution:
    def largestGoodInteger(self, num: str) -> str:
        for i in range(9, -1, -1):
            if (s := str(i) * 3) in num:
                return s
        return ""
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
