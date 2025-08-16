--- ❤️ ---

# 🚀 _Day 228. Maximum 69 Number_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/maximum-69-number/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int maximum69Number(int num) {
        string s = to_string(num);
        for (char& ch : s) {
            if (ch == '6') {
                ch = '9';
                break;
            }
        }
        return stoi(s);
    }
};
```

## Code (Java)

```java
class Solution {
    public int maximum69Number(int num) {
        return Integer.valueOf(String.valueOf(num).replaceFirst("6", "9"));
    }
}
```

## Code (Python)

```python
class Solution:
    def maximum69Number(self, num: int) -> int:
        return int(str(num).replace("6", "9", 1))
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
