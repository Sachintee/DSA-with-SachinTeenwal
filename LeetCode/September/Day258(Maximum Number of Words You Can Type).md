--- ❤️ ---

# 🚀 _Day 258. Maximum Number of Words You Can Type_ 🧠


The problem can be found at the following link: [Problem Link](https://leetcode.com/problems/maximum-number-of-words-you-can-type/)

## 🎯 **My Approach:**


## Code(C++)
```cpp
class Solution {
public:
    int canBeTypedWords(string text, string brokenLetters) {
        bool s[26]{};
        for (char c : brokenLetters) {
            s[c - 'a'] = true;
        }
        int ans = 0;
        stringstream ss(text);
        string w;
        while (ss >> w) {
            for (char c : w) {
                if (s[c - 'a']) {
                    --ans;
                    break;
                }
            }
            ++ans;
        }
        return ans;
    }
};
```

## Code (Java)

```java
class Solution {
    public int canBeTypedWords(String text, String brokenLetters) {
        boolean[] s = new boolean[26];
        for (char c : brokenLetters.toCharArray()) {
            s[c - 'a'] = true;
        }
        int ans = 0;
        for (String w : text.split(" ")) {
            for (char c : w.toCharArray()) {
                if (s[c - 'a']) {
                    --ans;
                    break;
                }
            }
            ++ans;
        }
        return ans;
    }
}
```

## Code (Python)

```python
class Solution:
    def canBeTypedWords(self, text: str, brokenLetters: str) -> int:
        s = set(brokenLetters)
        return sum(all(c not in s for c in w) for w in text.split())
```



## 🎯 **Contribution and Support:**

For discussions, questions, or doubts related to this solution, feel free to connect on Twitter(x): [Any Questions] (https://x.com/Sachin_Teenwal) Let’s make this learning journey more collaborative!

⭐ If you find this helpful, please give this repository a star! ⭐

---
