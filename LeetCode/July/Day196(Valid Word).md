--- ❤️ ---

# 🚀 _Day 196. Valid Word_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/valid-word/description/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    bool isValid(string word) {
        if (word.size() < 3) {
            return false;
        }
        bool has_vowel = false, has_consonant = false;
        bool vs[26]{};
        string vowels = "aeiou";
        for (char c : vowels) {
            vs[c - 'a'] = true;
        }
        for (char c : word) {
            if (isalpha(c)) {
                if (vs[tolower(c) - 'a']) {
                    has_vowel = true;
                } else {
                    has_consonant = true;
                }
            } else if (!isdigit(c)) {
                return false;
            }
        }
        return has_vowel && has_consonant;
    }
};
```

## Code (Java)

```java
class Solution {
    public boolean isValid(String word) {
        if (word.length() < 3) {
            return false;
        }
        boolean hasVowel = false, hasConsonant = false;
        boolean[] vs = new boolean[26];
        for (char c : "aeiou".toCharArray()) {
            vs[c - 'a'] = true;
        }
        for (char c : word.toCharArray()) {
            if (Character.isAlphabetic(c)) {
                if (vs[Character.toLowerCase(c) - 'a']) {
                    hasVowel = true;
                } else {
                    hasConsonant = true;
                }
            } else if (!Character.isDigit(c)) {
                return false;
            }
        }
        return hasVowel && hasConsonant;
    }
}
```

## Code (Python)

```python
class Solution:
    def isValid(self, word: str) -> bool:
        if len(word) < 3:
            return False
        has_vowel = has_consonant = False
        vs = set("aeiouAEIOU")
        for c in word:
            if not c.isalnum():
                return False
            if c.isalpha():
                if c in vs:
                    has_vowel = True
                else:
                    has_consonant = True
        return has_vowel and has_consonant
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
