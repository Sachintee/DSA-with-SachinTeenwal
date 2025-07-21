--- ❤️ ---

# 🚀 _Day 202. Delete Characters to Make Fancy String_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/delete-characters-to-make-fancy-string/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    string makeFancyString(string s) {
        string ans = "";
        for (int i = 0; i < s.length(); ++i) {
            char c = s[i];
            if (i < 2 || c != s[i - 1] || c != s[i - 2]) {
                ans += c;
            }
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public String makeFancyString(String s) {
        StringBuilder ans = new StringBuilder();
        for (int i = 0; i < s.length(); ++i) {
            char c = s.charAt(i);
            if (i < 2 || c != s.charAt(i - 1) || c != s.charAt(i - 2)) {
                ans.append(c);
            }
        }
        return ans.toString();
    }
}
```

## Code (Python)

```python
class Solution:
    def makeFancyString(self, s: str) -> str:
        ans = []
        for i, c in enumerate(s):
            if i < 2 or c != s[i - 1] or c != s[i - 2]:
                ans.append(c)
        return "".join(ans)
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
