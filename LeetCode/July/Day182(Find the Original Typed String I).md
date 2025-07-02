--- ❤️ ---

# 🚀 _Day 182. Find the Original Typed String I_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/find-the-original-typed-string-i/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int possibleStringCount(string word) {
        int f = 1;
        for (int i = 1; i < word.size(); ++i) {
            f += word[i] == word[i - 1];
        }
        return f;
    }
};
```

## Code (Java)

```java
class Solution {
    public int possibleStringCount(String word) {
        int f = 1;
        for (int i = 1; i < word.length(); ++i) {
            if (word.charAt(i) == word.charAt(i - 1)) {
                ++f;
            }
        }
        return f;
    }
}
```

## Code (Python)

```python
class Solution:
    def possibleStringCount(self, word: str) -> int:
        return 1 + sum(x == y for x, y in pairwise(word))
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
